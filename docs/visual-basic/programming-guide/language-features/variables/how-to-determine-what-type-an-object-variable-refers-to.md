---
title: "Postupy: Určení, na jaký typ proměnná objektu odkazuje (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5dd6785ecd48be3f0455de63b9e3f13a485ddbb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="a24f3-102">Postupy: Určení, na jaký typ proměnná objektu odkazuje (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a24f3-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="a24f3-103">Proměnné objektu obsahuje ukazatel na data, která je uložená na jiném místě.</span><span class="sxs-lookup"><span data-stu-id="a24f3-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="a24f3-104">Typ dat, můžete změnit za běhu.</span><span class="sxs-lookup"><span data-stu-id="a24f3-104">The type of that data can change during run time.</span></span> <span data-ttu-id="a24f3-105">V každém okamžiku můžete použít <xref:System.Type.GetTypeCode%2A> metoda k určení aktuální typ spuštění nebo [typeof – operátor](../../../../visual-basic/language-reference/operators/typeof-operator.md) zjistit, jestli aktuální běhového typu je kompatibilní s zadaného typu.</span><span class="sxs-lookup"><span data-stu-id="a24f3-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="a24f3-106">Chcete-li zjistit, že že přesný typ proměnná objektu aktuálně odkazuje na</span><span class="sxs-lookup"><span data-stu-id="a24f3-106">To determine the exact type an object variable currently refers to</span></span>  
  
1.  <span data-ttu-id="a24f3-107">Na proměnnou objekt volání <xref:System.Object.GetType%2A> metoda pro načtení <xref:System.Type?displayProperty=nameWithType> objektu.</span><span class="sxs-lookup"><span data-stu-id="a24f3-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  <span data-ttu-id="a24f3-108">Na <xref:System.Type?displayProperty=nameWithType> třídy, volejte metodu sdílené <xref:System.Type.GetTypeCode%2A> načíst <xref:System.TypeCode> hodnota výčtu pro typ objektu.</span><span class="sxs-lookup"><span data-stu-id="a24f3-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="a24f3-109">Můžete otestovat <xref:System.TypeCode> hodnoty výčtu s kteroukoli členy výčtu jsou zájmu, například `Double`.</span><span class="sxs-lookup"><span data-stu-id="a24f3-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="a24f3-110">K určení, zda objekt je kompatibilní s typem zadaný typ proměnné</span><span class="sxs-lookup"><span data-stu-id="a24f3-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="a24f3-111">Použití `TypeOf` operátor v kombinaci s [je operátor](../../../../visual-basic/language-reference/operators/is-operator.md) k testování objekt s `TypeOf`... `Is` výraz.</span><span class="sxs-lookup"><span data-stu-id="a24f3-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="a24f3-112">`TypeOf`... `Is` výraz vrátí `True` Pokud objekt je spuštění typ je kompatibilní se zadaným typem.</span><span class="sxs-lookup"><span data-stu-id="a24f3-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="a24f3-113">Kritéria pro kompatibilitu závisí na tom, zda zadaný typ je třída, struktura nebo rozhraní.</span><span class="sxs-lookup"><span data-stu-id="a24f3-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="a24f3-114">Typy jsou obecně kompatibilní Pokud objekt je stejného typu jako, dědí z nebo implementuje zadaného typu.</span><span class="sxs-lookup"><span data-stu-id="a24f3-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="a24f3-115">Další informace najdete v tématu [typeof – operátor](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a24f3-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a24f3-116">Probíhá kompilace kódu</span><span class="sxs-lookup"><span data-stu-id="a24f3-116">Compiling the Code</span></span>  
 <span data-ttu-id="a24f3-117">Všimněte si, že zadaný typ nemůže být proměnné nebo výrazu.</span><span class="sxs-lookup"><span data-stu-id="a24f3-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="a24f3-118">Musí být název určitého typu, například třída, struktura nebo rozhraní.</span><span class="sxs-lookup"><span data-stu-id="a24f3-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="a24f3-119">Jedná se o vnitřní typy, jako `Integer` a `String`.</span><span class="sxs-lookup"><span data-stu-id="a24f3-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24f3-120">Viz také</span><span class="sxs-lookup"><span data-stu-id="a24f3-120">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [<span data-ttu-id="a24f3-121">Objektové proměnné</span><span class="sxs-lookup"><span data-stu-id="a24f3-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="a24f3-122">Hodnoty proměnné objektu</span><span class="sxs-lookup"><span data-stu-id="a24f3-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="a24f3-123">Object – datový typ</span><span class="sxs-lookup"><span data-stu-id="a24f3-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)