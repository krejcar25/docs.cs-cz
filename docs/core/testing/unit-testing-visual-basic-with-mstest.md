---
title: "Testování jazyka Visual Basic v .NET Core pomocí testovacích dotnet a Mstestu částí"
description: "Další koncepty test jednotky v .NET Core prostřednictvím interaktivní prostředí vytváření ukázkové řešení Visual Basic podrobné pomocí Mstestu."
author: billwagner
ms.author: wiwagn
ms.date: 09/01/2017
ms.topic: article
dev_langs: vb
ms.prod: .net-core
ms.openlocfilehash: b656ae4746691f2e72eaa666542e98d4abc91069
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-mstest"></a><span data-ttu-id="420d6-103">Knihovny jazyka Visual Basic .NET Core pomocí testovacích dotnet a Mstestu testování částí</span><span class="sxs-lookup"><span data-stu-id="420d6-103">Unit testing Visual Basic .NET Core libraries using dotnet test and MStest</span></span>

<span data-ttu-id="420d6-104">Tento kurz vás provede interaktivní prostředí vytváření ukázkové řešení podrobné další koncepty testování částí.</span><span class="sxs-lookup"><span data-stu-id="420d6-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="420d6-105">Pokud chcete postupovat v kurzu pomocí předdefinovaných řešení, [zobrazení nebo stažení ukázkového kódu](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-mstest/) před zahájením.</span><span class="sxs-lookup"><span data-stu-id="420d6-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-mstest/) before you begin.</span></span> <span data-ttu-id="420d6-106">Pokyny ke stažení najdete v tématu [ukázky a výukové programy](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="420d6-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="420d6-107">Vytvoření projektu zdroje</span><span class="sxs-lookup"><span data-stu-id="420d6-107">Creating the source project</span></span>

<span data-ttu-id="420d6-108">Otevřete okno prostředí.</span><span class="sxs-lookup"><span data-stu-id="420d6-108">Open a shell window.</span></span> <span data-ttu-id="420d6-109">Vytvořte adresář s názvem *testování pomocí dotnet – testování* pro uložení řešení.</span><span class="sxs-lookup"><span data-stu-id="420d6-109">Create a directory called *unit-testing-using-dotnet-test* to hold the solution.</span></span>
<span data-ttu-id="420d6-110">Uvnitř tohoto nového adresáře, spusťte [ `dotnet new sln` ](../tools/dotnet-new.md) k vytvoření nové řešení.</span><span class="sxs-lookup"><span data-stu-id="420d6-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="420d6-111">Tento postup je snazší správa knihovny tříd a projektu testování částí.</span><span class="sxs-lookup"><span data-stu-id="420d6-111">This practice makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="420d6-112">V adresáři řešení vytvořit *PrimeService* adresáře.</span><span class="sxs-lookup"><span data-stu-id="420d6-112">Inside the solution directory, create a *PrimeService* directory.</span></span> <span data-ttu-id="420d6-113">Proto pokud máte následující strukturu adresáře a souboru:</span><span class="sxs-lookup"><span data-stu-id="420d6-113">You have the following directory and file structure thus far:</span></span>

```
/unit-testing-vb-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
```

<span data-ttu-id="420d6-114">Ujistěte se, *PrimeService* aktuální adresář a spusťte [ `dotnet new classlib -lang VB` ](../tools/dotnet-new.md) a vytvořte tak projekt zdroje.</span><span class="sxs-lookup"><span data-stu-id="420d6-114">Make *PrimeService* the current directory and run [`dotnet new classlib -lang VB`](../tools/dotnet-new.md) to create the source project.</span></span> <span data-ttu-id="420d6-115">Přejmenování *Class1.VB* k *PrimeService.VB*.</span><span class="sxs-lookup"><span data-stu-id="420d6-115">Rename *Class1.VB* to *PrimeService.VB*.</span></span> <span data-ttu-id="420d6-116">Použití vývoje řízeného testováním (TDD), vytvořte na selhání implementace `PrimeService` třídy:</span><span class="sxs-lookup"><span data-stu-id="420d6-116">To use test-driven development (TDD), you create a failing implementation of the `PrimeService` class:</span></span>

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

<span data-ttu-id="420d6-117">Změna adresáře zpět do *jednotky – testování vb – pomocí stest* adresáře.</span><span class="sxs-lookup"><span data-stu-id="420d6-117">Change the directory back to the *unit-testing-vb-using-stest* directory.</span></span> <span data-ttu-id="420d6-118">Spustit [ `dotnet sln add .\PrimeService\PrimeService.vbproj` ](../tools/dotnet-sln.md) přidání projektu knihovny tříd do řešení.</span><span class="sxs-lookup"><span data-stu-id="420d6-118">Run [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="420d6-119">Vytvoření projektu testů</span><span class="sxs-lookup"><span data-stu-id="420d6-119">Creating the test project</span></span>

<span data-ttu-id="420d6-120">Dále vytvořte *PrimeService.Tests* adresáře.</span><span class="sxs-lookup"><span data-stu-id="420d6-120">Next, create the *PrimeService.Tests* directory.</span></span> <span data-ttu-id="420d6-121">Zobrazí následující osnova adresářovou strukturu:</span><span class="sxs-lookup"><span data-stu-id="420d6-121">The following outline shows the directory structure:</span></span>

```
/unit-testing-vb-using-mstest
    unit-testing-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

<span data-ttu-id="420d6-122">Ujistěte se, *PrimeService.Tests* adresář aktuální adresář a vytvoření nového projektu pomocí [ `dotnet new mstest -lang VB` ](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="420d6-122">Make the *PrimeService.Tests* directory the current directory and create a new project using [`dotnet new mstest -lang VB`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="420d6-123">Tento příkaz vytvoří testovací projekt, který používá xUnit jako knihovně testu.</span><span class="sxs-lookup"><span data-stu-id="420d6-123">This command creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="420d6-124">Nástroj test runner v nakonfiguruje vygenerované šablony *PrimeServiceTests.vbproj*:</span><span class="sxs-lookup"><span data-stu-id="420d6-124">The generated template configures the test runner in the *PrimeServiceTests.vbproj*:</span></span>

```xml
<ItemGroup>
<PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
<PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
<PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="420d6-125">K testovacímu projektu vyžaduje další balíčky k vytváření a spouštění testování částí.</span><span class="sxs-lookup"><span data-stu-id="420d6-125">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="420d6-126">`dotnet new`v předchozím kroku přidat Mstestu a Mstestu runner.</span><span class="sxs-lookup"><span data-stu-id="420d6-126">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="420d6-127">Nyní přidejte `PrimeService` knihovny tříd jako další závislosti do projektu.</span><span class="sxs-lookup"><span data-stu-id="420d6-127">Now, add the `PrimeService` class library as another dependency to the project.</span></span> <span data-ttu-id="420d6-128">Použití [ `dotnet add reference` ](../tools/dotnet-add-reference.md) příkaz:</span><span class="sxs-lookup"><span data-stu-id="420d6-128">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

<span data-ttu-id="420d6-129">Zobrazí celý soubor v [ukázky úložiště](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) na Githubu.</span><span class="sxs-lookup"><span data-stu-id="420d6-129">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService.Tests.vbproj) on GitHub.</span></span>

<span data-ttu-id="420d6-130">Máte následující rozložení konečné řešení:</span><span class="sxs-lookup"><span data-stu-id="420d6-130">You have the following final solution layout:</span></span>

```
/unit-testing-vb-using-mstest
    unit-testing-vb-using-mstest.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

<span data-ttu-id="420d6-131">Spuštění [ `dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj` ](../tools/dotnet-sln.md) v *jednotky – testování vb – pomocí mstestu* adresáře.</span><span class="sxs-lookup"><span data-stu-id="420d6-131">Execute [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) in the *unit-testing-vb-using-mstest* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="420d6-132">Vytvoření prvního testu</span><span class="sxs-lookup"><span data-stu-id="420d6-132">Creating the first test</span></span>

<span data-ttu-id="420d6-133">Volá TDD přístup pro zápis jeden selhání test, což předat a zopakováním postupu.</span><span class="sxs-lookup"><span data-stu-id="420d6-133">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="420d6-134">Odebrat *UnitTest1.vb* z *PrimeService.Tests* adresáře a vytvořte nový soubor jazyka Visual Basic s názvem *PrimeService_IsPrimeShould.VB*.</span><span class="sxs-lookup"><span data-stu-id="420d6-134">Remove *UnitTest1.vb* from the *PrimeService.Tests* directory and create a new Visual Basic file named *PrimeService_IsPrimeShould.VB*.</span></span> <span data-ttu-id="420d6-135">Přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="420d6-135">Add the following code:</span></span>

```vb
Imports Microsoft.VisualStudio.TestTools.UnitTesting

Namespace PrimeService.Tests
    <TestClass>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <TestMethod>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

<span data-ttu-id="420d6-136">`<TestClass>` Atribut určuje třídu, která obsahuje testy.</span><span class="sxs-lookup"><span data-stu-id="420d6-136">The `<TestClass>` attribute indicates a class that contains tests.</span></span> <span data-ttu-id="420d6-137">`<TestMethod>` Atribut označuje metodu, která spustí nástroj test runner.</span><span class="sxs-lookup"><span data-stu-id="420d6-137">The `<TestMethod>` attribute denotes a method that is run by the test runner.</span></span> <span data-ttu-id="420d6-138">Z *jednotky – testování vb – pomocí mstestu*, provést [ `dotnet test` ](../tools/dotnet-test.md) vytvářet testy a knihovny tříd a poté spusťte testy.</span><span class="sxs-lookup"><span data-stu-id="420d6-138">From the *unit-testing-vb-using-mstest*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="420d6-139">Nástroj test runner xUnit obsahuje vstupní bod programu ke spuštění testů.</span><span class="sxs-lookup"><span data-stu-id="420d6-139">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="420d6-140">`dotnet test`Spustí nástroj test runner pomocí projektu testů jednotek, které jste vytvořili.</span><span class="sxs-lookup"><span data-stu-id="420d6-140">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="420d6-141">Test se nezdaří.</span><span class="sxs-lookup"><span data-stu-id="420d6-141">Your test fails.</span></span> <span data-ttu-id="420d6-142">Nevytvořili jste ještě implementace.</span><span class="sxs-lookup"><span data-stu-id="420d6-142">You haven't created the implementation yet.</span></span> <span data-ttu-id="420d6-143">Psaní kódu nejjednodušší v, aby tento test `PrimeService` třídu, která funguje:</span><span class="sxs-lookup"><span data-stu-id="420d6-143">Make this test by writing the simplest code in the `PrimeService` class that works:</span></span>

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

<span data-ttu-id="420d6-144">V *jednotky – testování vb – pomocí mstestu* spusťte `dotnet test` znovu.</span><span class="sxs-lookup"><span data-stu-id="420d6-144">In the *unit-testing-vb-using-mstest* directory, run `dotnet test` again.</span></span> <span data-ttu-id="420d6-145">`dotnet test` Příkaz spustí sestavení pro `PrimeService` projektu a pak `PrimeService.Tests` projektu.</span><span class="sxs-lookup"><span data-stu-id="420d6-145">The `dotnet test` command runs a build for the `PrimeService` project and then for the `PrimeService.Tests` project.</span></span> <span data-ttu-id="420d6-146">Po sestavení obou projektů, spustí se tento jeden test.</span><span class="sxs-lookup"><span data-stu-id="420d6-146">After building both projects, it runs this single test.</span></span> <span data-ttu-id="420d6-147">Pak předá.</span><span class="sxs-lookup"><span data-stu-id="420d6-147">It passes.</span></span>

## <a name="adding-more-features"></a><span data-ttu-id="420d6-148">Přidání další funkce</span><span class="sxs-lookup"><span data-stu-id="420d6-148">Adding more features</span></span>

<span data-ttu-id="420d6-149">Teď, když jste udělali jeden testovací předání, je čas zapsat informace.</span><span class="sxs-lookup"><span data-stu-id="420d6-149">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="420d6-150">Existuje několik dalších jednoduchý případů pro prvočísel: 0, -1.</span><span class="sxs-lookup"><span data-stu-id="420d6-150">There are a few other simple cases for prime numbers: 0, -1.</span></span> <span data-ttu-id="420d6-151">Můžete přidat jako nový testování pomocí těchto případech `<TestMethod>` atribut, ale které rychle stane zdlouhavé.</span><span class="sxs-lookup"><span data-stu-id="420d6-151">You could add those cases as new tests with the `<TestMethod>` attribute, but that quickly becomes tedious.</span></span> <span data-ttu-id="420d6-152">Existují další xUnit atributy, které vám umožní zápisu sada testů, podobně jako.</span><span class="sxs-lookup"><span data-stu-id="420d6-152">There are other xUnit attributes that enable you to write a suite of similar tests.</span></span>  <span data-ttu-id="420d6-153">A `<DataTestMethod>` atribut představuje sada testů, které provést stejný kód, ale mají jinou vstupní argumenty.</span><span class="sxs-lookup"><span data-stu-id="420d6-153">A `<DataTestMethod>` attribute represents a suite of tests that execute the same code but have different input arguments.</span></span> <span data-ttu-id="420d6-154">Můžete použít `<DataRow>` atribut zadat hodnoty pro tyto vstupy.</span><span class="sxs-lookup"><span data-stu-id="420d6-154">You can use the `<DataRow>` attribute to specify values for those inputs.</span></span>

<span data-ttu-id="420d6-155">Místo vytváření nové testů, platí tyto dva atributy pro vytvoření jedné teoreticky.</span><span class="sxs-lookup"><span data-stu-id="420d6-155">Instead of creating new tests, apply these two attributes to create a single theory.</span></span> <span data-ttu-id="420d6-156">Teorie je metoda, která porovná několik hodnoty menší než dva, což je nejnižší prime číslo:</span><span class="sxs-lookup"><span data-stu-id="420d6-156">The theory is a method that tests several values less than two, which is the lowest prime number:</span></span>

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

<span data-ttu-id="420d6-157">Spustit `dotnet test`, a dvě z nich testy nezdaří.</span><span class="sxs-lookup"><span data-stu-id="420d6-157">Run `dotnet test`, and two of these tests fail.</span></span> <span data-ttu-id="420d6-158">Chcete-li všechny testy průchodu, změnit `if` klauzule na začátku metody:</span><span class="sxs-lookup"><span data-stu-id="420d6-158">To make all of the tests pass, change the `if` clause at the beginning of the method:</span></span>

```vb
if candidate < 2
```

<span data-ttu-id="420d6-159">Pokračujte k iteraci v přidáním další testy, další teorií a další kód v knihovně hlavní.</span><span class="sxs-lookup"><span data-stu-id="420d6-159">Continue to iterate by adding more tests, more theories, and more code in the main library.</span></span> <span data-ttu-id="420d6-160">Máte [dokončení verzi testy](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) a [dokončení implementace knihovny](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService/PrimeService.vb).</span><span class="sxs-lookup"><span data-stu-id="420d6-160">You have the [finished version of the tests](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.vb) and the [complete implementation of the library](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-using-mstest/PrimeService/PrimeService.vb).</span></span>

<span data-ttu-id="420d6-161">Když jste sestavili malé knihovny a sadu testů jednotek pro danou knihovnu.</span><span class="sxs-lookup"><span data-stu-id="420d6-161">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="420d6-162">Řešení si strukturovaná, tak, aby přidání nové balíčky a testy je součástí normálním pracovním postupu.</span><span class="sxs-lookup"><span data-stu-id="420d6-162">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="420d6-163">Jste soustředí většinu čas a úsilí na řešení cílů aplikace.</span><span class="sxs-lookup"><span data-stu-id="420d6-163">You've concentrated most of your time and effort on solving the goals of the application.</span></span>