---
title: "Postupy: výpočet hodnot sloupce v textovém souboru CSV (LINQ) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88b2b9f3-c82e-41f3-b1b4-26ede5973a02
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d57376ca2741801d6aee858688f00cba245a225d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-compute-column-values-in-a-csv-text-file-linq-visual-basic"></a><span data-ttu-id="31f3c-102">Postupy: výpočet hodnot sloupce v textovém souboru CSV (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31f3c-102">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="31f3c-103">Tento příklad ukazuje, jak provádět agregační výpočtů, jako je například součtu, průměru, Min a Max pro sloupce soubor .csv.</span><span class="sxs-lookup"><span data-stu-id="31f3c-103">This example shows how to perform aggregate computations such as Sum, Average, Min, and Max on the columns of a .csv file.</span></span> <span data-ttu-id="31f3c-104">Příklad zásady, které jsou zobrazeny v tomto poli je použít pro jiné typy strukturovaných textových.</span><span class="sxs-lookup"><span data-stu-id="31f3c-104">The example principles that are shown here can be applied to other types of structured text.</span></span>  
  
### <a name="to-create-the-source-file"></a><span data-ttu-id="31f3c-105">Chcete-li vytvořit zdrojový soubor</span><span class="sxs-lookup"><span data-stu-id="31f3c-105">To create the source file</span></span>  
  
1.  <span data-ttu-id="31f3c-106">Zkopírujte následující řádky do souboru, který je pojmenován scores.csv a uložit ve složce projektu.</span><span class="sxs-lookup"><span data-stu-id="31f3c-106">Copy the following lines into a file that is named scores.csv and save it in your project folder.</span></span> <span data-ttu-id="31f3c-107">Předpokládají, že první sloupec představuje student ID a následné sloupce představují skóre ze čtyř zkoušek pro aplikaci.</span><span class="sxs-lookup"><span data-stu-id="31f3c-107">Assume that the first column represents a student ID, and subsequent columns represent scores from four exams.</span></span>  
  
    ```  
    111, 97, 92, 81, 60  
    112, 75, 84, 91, 39  
    113, 88, 94, 65, 91  
    114, 97, 89, 85, 82  
    115, 35, 72, 91, 70  
    116, 99, 86, 90, 94  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    119, 68, 79, 88, 92  
    120, 99, 82, 81, 79  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    ```  
  
## <a name="example"></a><span data-ttu-id="31f3c-108">Příklad</span><span class="sxs-lookup"><span data-stu-id="31f3c-108">Example</span></span>  
  
```vb  
Class SumColumns  
  
    Public Shared Sub Main()  
  
        Dim lines As String() = System.IO.File.ReadAllLines("../../../scores.csv")  
  
        ' Specifies the column to compute  
        ' This value could be passed in at runtime.  
        Dim exam = 3  
  
        ' Spreadsheet format:  
        ' Student ID    Exam#1  Exam#2  Exam#3  Exam#4  
        ' 111,          97,     92,     81,     60  
        ' one is added to skip over the first column  
        ' which holds the student ID.  
        SumColumn(lines, exam + 1)  
        Console.WriteLine()  
        MultiColumns(lines)  
  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit...")  
        Console.ReadKey()  
  
    End Sub  
  
    Shared Sub SumColumn(ByVal lines As IEnumerable(Of String), ByVal col As Integer)  
  
        ' This query performs two steps:  
        ' split the string into a string array  
        ' convert the specified element to  
        ' integer and select it.  
        Dim columnQuery = From line In lines   
                           Let x = line.Split(",")   
                           Select Convert.ToInt32(x(col))  
  
        ' Execute and cache the results for performance.  
        ' Only needed with very large files.  
        Dim results = columnQuery.ToList()  
  
        ' Perform aggregate calculations   
        ' on the column specified by col.  
        Dim avgScore = Aggregate score In results Into Average(score)  
        Dim minScore = Aggregate score In results Into Min(score)  
        Dim maxScore = Aggregate score In results Into Max(score)  
  
        Console.WriteLine("Single Column Query:")  
        Console.WriteLine("Exam #{0}: Average:{1:##.##} High Score:{2} Low Score:{3}",   
                     col, avgScore, maxScore, minScore)  
  
    End Sub  
  
    Shared Sub MultiColumns(ByVal lines As IEnumerable(Of String))  
  
        Console.WriteLine("Multi Column Query:")  
  
        ' Create the query. It will produce nested sequences.   
        ' multiColQuery performs these steps:  
        ' 1) convert the string to a string array  
        ' 2) skip over the "Student ID" column and take the rest  
        ' 3) convert each field to an int and select that   
        '    entire sequence as one row in the results.  
        Dim multiColQuery = From line In lines   
                            Let fields = line.Split(",")   
                            Select From str In fields Skip 1   
                                        Select Convert.ToInt32(str)  
  
        Dim results = multiColQuery.ToList()  
  
        ' Find out how many columns we have.  
        Dim columnCount = results(0).Count()  
  
        ' Perform aggregate calculations on each column.              
        ' One loop for each score column in scores.  
        ' We can use a for loop because we have already  
        ' executed the multiColQuery in the call to ToList.  
  
        For j As Integer = 0 To columnCount - 1  
            Dim column = j  
            Dim res2 = From row In results   
                       Select row.ElementAt(column)  
  
            ' Perform aggregate calculations   
            ' on the column specified by col.  
            Dim avgScore = Aggregate score In res2 Into Average(score)  
            Dim minScore = Aggregate score In res2 Into Min(score)  
            Dim maxScore = Aggregate score In res2 Into Max(score)  
  
            ' Add 1 to column numbers because exams in this course start with #1  
            Console.WriteLine("Exam #{0} Average: {1:##.##} High Score: {2} Low Score: {3}",   
                              column + 1, avgScore, maxScore, minScore)  
  
        Next  
    End Sub  
  
End Class  
' Output:  
' Single Column Query:  
' Exam #4: Average:76.92 High Score:94 Low Score:39  
  
' Multi Column Query:  
' Exam #1 Average: 86.08 High Score: 99 Low Score: 35  
' Exam #2 Average: 86.42 High Score: 94 Low Score: 72  
' Exam #3 Average: 84.75 High Score: 91 Low Score: 65  
' Exam #4 Average: 76.92 High Score: 94 Low Score: 39  
```  
  
 <span data-ttu-id="31f3c-109">Dotaz funguje tak, že pomocí <xref:System.String.Split%2A> způsobů, jak převést jednotlivé řádky textu do pole.</span><span class="sxs-lookup"><span data-stu-id="31f3c-109">The query works by using the <xref:System.String.Split%2A> method to convert each line of text into an array.</span></span> <span data-ttu-id="31f3c-110">Každý element pole představuje sloupec.</span><span class="sxs-lookup"><span data-stu-id="31f3c-110">Each array element represents a column.</span></span> <span data-ttu-id="31f3c-111">Nakonec text v jednotlivých sloupcích jsou převedeny na jeho číselnému znázornění.</span><span class="sxs-lookup"><span data-stu-id="31f3c-111">Finally, the text in each column is converted to its numeric representation.</span></span> <span data-ttu-id="31f3c-112">Pokud se soubor nachází soubor tabulátorem, stačí aktualizovat argument ve `Split` metodu `\t`.</span><span class="sxs-lookup"><span data-stu-id="31f3c-112">If your file is a tab-separated file, just update the argument in the `Split` method to `\t`.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31f3c-113">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="31f3c-113">Compiling the Code</span></span>  
 <span data-ttu-id="31f3c-114">Vytvoření projektu, jehož cílem rozhraní .NET Framework verze 3.5 nebo vyšší s odkazem na System.Core.dll a `Imports` příkaz pro obor názvů System.Linq.</span><span class="sxs-lookup"><span data-stu-id="31f3c-114">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f3c-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="31f3c-115">See Also</span></span>  
 [<span data-ttu-id="31f3c-116">LINQ a řetězce (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31f3c-116">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="31f3c-117">LINQ a souborové adresáře (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31f3c-117">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)