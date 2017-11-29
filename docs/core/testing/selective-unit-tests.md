---
title: "Testy spuštění selektivní jednotek"
description: "Ukazuje, jak se použije ke spuštění testů jednotek selektivní test příkazem dotnet výraz filtru."
keywords: "Testování částí rozhraní .NET, .NET core, selektivní testu"
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13d01272-bbf8-456c-a97a-560001d1a7f2
ms.openlocfilehash: af832d04d2cba530a93710a90701ab119a66deef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="67b85-104">Testy spuštění selektivní jednotek</span><span class="sxs-lookup"><span data-stu-id="67b85-104">Running selective unit tests</span></span>

<span data-ttu-id="67b85-105">Následující příklady použití `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="67b85-105">The following examples use `dotnet test`.</span></span> <span data-ttu-id="67b85-106">Pokud používáte `vstest.console.exe`, nahraďte `--filter ` s `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="67b85-106">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="67b85-107">MSTest</span><span class="sxs-lookup"><span data-stu-id="67b85-107">MSTest</span></span>

```csharp
namespace MSTestNamespace
{
    using Microsoft.VisualStudio.TestTools.UnitTesting;

    [TestClass]
    public class UnitTestClass1
    {
        [Priority(2)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [TestCategory("CategoryA")]
        [Priority(3)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="67b85-108">Výraz</span><span class="sxs-lookup"><span data-stu-id="67b85-108">Expression</span></span> | <span data-ttu-id="67b85-109">Výsledek</span><span class="sxs-lookup"><span data-stu-id="67b85-109">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="67b85-110">Spuštění testů, jehož `FullyQualifiedName` obsahuje `Method`.</span><span class="sxs-lookup"><span data-stu-id="67b85-110">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="67b85-111">K dispozici v `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="67b85-111">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="67b85-112">Spustí testy, jejichž název obsahuje `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="67b85-112">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="67b85-113">Spustí testy, které jsou ve třídě `MSTestNamespace.UnitTestClass1`.</span><span class="sxs-lookup"><span data-stu-id="67b85-113">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="67b85-114">**Poznámka:** `ClassName` hodnota musí mít obor názvů, takže `ClassName=UnitTestClass1` nebude fungovat.</span><span class="sxs-lookup"><span data-stu-id="67b85-114">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="67b85-115">Spustí všechny testy kromě `MSTestNamespace.UnitTestClass1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="67b85-115">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="67b85-116">Spustí testy, které jsou opatřen poznámkou `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="67b85-116">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="67b85-117">Spustí testy, které jsou opatřen poznámkou `[Priority(3)]`.</span><span class="sxs-lookup"><span data-stu-id="67b85-117">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="67b85-118">**Poznámka:** `Priority~3` je neplatná hodnota, protože není řetězec.</span><span class="sxs-lookup"><span data-stu-id="67b85-118">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="67b85-119">**Podmíněné operátory pomocí | a&amp;**</span><span class="sxs-lookup"><span data-stu-id="67b85-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="67b85-120">Výraz</span><span class="sxs-lookup"><span data-stu-id="67b85-120">Expression</span></span> | <span data-ttu-id="67b85-121">Výsledek</span><span class="sxs-lookup"><span data-stu-id="67b85-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="67b85-122">Spustí testy, které mají `UnitTestClass1` v `FullyQualifiedName` **nebo** `TestCategory` je `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="67b85-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="67b85-123">Spustí testy, které mají `UnitTestClass1` v `FullyQualifiedName` **a** `TestCategory` je `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="67b85-123">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="67b85-124">Spustí testy, které mají buď `FullyQualifiedName` obsahující `UnitTestClass1` **a** `TestCategory` je `CategoryA` **nebo** `Priority` je 1.</span><span class="sxs-lookup"><span data-stu-id="67b85-124">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="67b85-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="67b85-125">xUnit</span></span>

```csharp
namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "bvt")]
        [Trait("Priority", "1")]
        [Fact]
        public void foo()
        {
        }

        [Trait("Category", "Nightly")]
        [Trait("Priority", "2")]
        [Fact]
        public void bar()
        {
        }
    }
}
```

| <span data-ttu-id="67b85-126">Výraz</span><span class="sxs-lookup"><span data-stu-id="67b85-126">Expression</span></span> | <span data-ttu-id="67b85-127">Výsledek</span><span class="sxs-lookup"><span data-stu-id="67b85-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="67b85-128">Spouští pouze jeden test `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="67b85-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="67b85-129">Spustí všechny testy kromě `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="67b85-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="67b85-130">Spustí testy, jejichž název zobrazení obsahuje `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="67b85-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="67b85-131">V příkladu kódu, jsou definované vlastnosti s klíči `Category` a `Priority` lze použít pro filtrování.</span><span class="sxs-lookup"><span data-stu-id="67b85-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="67b85-132">Výraz</span><span class="sxs-lookup"><span data-stu-id="67b85-132">Expression</span></span> | <span data-ttu-id="67b85-133">Výsledek</span><span class="sxs-lookup"><span data-stu-id="67b85-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="67b85-134">Spuštění testů, jehož `FullyQualifiedName` obsahuje `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="67b85-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="67b85-135">K dispozici v `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="67b85-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="67b85-136">Spustí testy, které mají `[Trait("Category", "bvt")]`.</span><span class="sxs-lookup"><span data-stu-id="67b85-136">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="67b85-137">**Podmíněné operátory pomocí | a&amp;**</span><span class="sxs-lookup"><span data-stu-id="67b85-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="67b85-138">Výraz</span><span class="sxs-lookup"><span data-stu-id="67b85-138">Expression</span></span> | <span data-ttu-id="67b85-139">Výsledek</span><span class="sxs-lookup"><span data-stu-id="67b85-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="67b85-140">Spustí testy, které má `TestClass1` v `FullyQualifiedName` **nebo** `Category` je `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="67b85-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="67b85-141">Spustí testy, které má `TestClass1` v `FullyQualifiedName` **a** `Category` je `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="67b85-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="67b85-142">Spustí testy, které mají buď `FullyQualifiedName` obsahující `TestClass1` **a** `Category` je `CategoryA` **nebo** `Priority` je 1.</span><span class="sxs-lookup"><span data-stu-id="67b85-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |