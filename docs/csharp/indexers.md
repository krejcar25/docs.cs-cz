---
title: Indexery
description: "Další informace o indexery C# a jak implementovat indexovaných vlastností, které jsou vlastnosti odkazovat pomocí jednoho nebo více argumentů."
keywords: "Rozhraní .NET, .NET core"
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0e9496da-e766-45a9-b92b-91820d4a350e
ms.openlocfilehash: 32e090524f414ef93b8481a8ad356b313191d8b9
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/08/2017
---
# <a name="indexers"></a><span data-ttu-id="f18ae-104">Indexery</span><span class="sxs-lookup"><span data-stu-id="f18ae-104">Indexers</span></span>

<span data-ttu-id="f18ae-105">*Indexery* jsou podobná vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="f18ae-105">*Indexers* are similar to properties.</span></span> <span data-ttu-id="f18ae-106">V mnoha směrech indexery sestavení na stejné funkce jazyka jako [vlastnosti](properties.md).</span><span class="sxs-lookup"><span data-stu-id="f18ae-106">In many ways indexers build on the same language features as [properties](properties.md).</span></span> <span data-ttu-id="f18ae-107">Povolit indexery *indexované* vlastnosti: vlastnosti odkazovat pomocí jednoho nebo více argumentů.</span><span class="sxs-lookup"><span data-stu-id="f18ae-107">Indexers enable *indexed* properties: properties referenced using one or more arguments.</span></span> <span data-ttu-id="f18ae-108">Těchto argumentů zadejte index do některé kolekce hodnot.</span><span class="sxs-lookup"><span data-stu-id="f18ae-108">Those arguments provide an index into some collection of values.</span></span>

## <a name="indexer-syntax"></a><span data-ttu-id="f18ae-109">Indexer syntaxe</span><span class="sxs-lookup"><span data-stu-id="f18ae-109">Indexer Syntax</span></span>

<span data-ttu-id="f18ae-110">Indexer přistupujete prostřednictvím název proměnné a hranaté závorky.</span><span class="sxs-lookup"><span data-stu-id="f18ae-110">You access an indexer through a variable name and square brackets .</span></span> <span data-ttu-id="f18ae-111">Umístěte argumenty indexer v závorkách:</span><span class="sxs-lookup"><span data-stu-id="f18ae-111">You place the indexer arguments inside the brackets:</span></span>

```csharp
var item = someObject["key"];
someObject["AnotherKey"] = item;
```

<span data-ttu-id="f18ae-112">Deklarovat indexery pomocí `this` – klíčové slovo jako název vlastnosti a deklarace argumenty v rámci hranaté závorky.</span><span class="sxs-lookup"><span data-stu-id="f18ae-112">You declare indexers using the `this` keyword as the property name, and declaring the arguments within square brackets.</span></span> <span data-ttu-id="f18ae-113">Toto prohlášení odpovídá využití uvedené v předchozím odstavci:</span><span class="sxs-lookup"><span data-stu-id="f18ae-113">This declaration would match the usage shown in the previous paragraph:</span></span>

```csharp
public int this[string key]
{
    get { return storage.Find(key); }
    set { storage.SetAt(key, value); }
}
```

<span data-ttu-id="f18ae-114">Z tohoto příkladu počáteční uvidíte vztah mezi syntaxe pro vlastnosti a indexery.</span><span class="sxs-lookup"><span data-stu-id="f18ae-114">From this initial example, you can see the relationship between the syntax for properties and for indexers.</span></span> <span data-ttu-id="f18ae-115">Tato analogie představuje prostřednictvím většiny pravidel syntaxe pro indexování.</span><span class="sxs-lookup"><span data-stu-id="f18ae-115">This analogy carries through most of the syntax rules for indexers.</span></span> <span data-ttu-id="f18ae-116">Indexery může mít libovolný platný přístup modifikátory (veřejné, chráněné interní, chráněné, interní, privátní nebo privátní chráněné).</span><span class="sxs-lookup"><span data-stu-id="f18ae-116">Indexers can have any valid access modifiers (public, protected internal, protected, internal, private or private protected).</span></span> <span data-ttu-id="f18ae-117">Se může být zapečetěné, virtuální nebo abstraktní.</span><span class="sxs-lookup"><span data-stu-id="f18ae-117">They may be sealed, virtual, or abstract.</span></span> <span data-ttu-id="f18ae-118">Stejně jako u vlastnosti, můžete zadat jiný přístup modifikátory pro get a nastavit accesssors v indexer.</span><span class="sxs-lookup"><span data-stu-id="f18ae-118">As with properties, you can specify different access modifiers for the get and set accesssors in an indexer.</span></span>
<span data-ttu-id="f18ae-119">Můžete také určit indexery jen pro čtení (Díky vynechání přistupující objekt set), nebo jen pro zápis indexery (Díky vynechání přistupující objekt get).</span><span class="sxs-lookup"><span data-stu-id="f18ae-119">You may also specify read-only indexers (by omitting the set accessor), or write-only indexers (by omitting the get accessor).</span></span>

<span data-ttu-id="f18ae-120">Můžete použít prakticky vše, co zjistíte z práce s vlastností indexery.</span><span class="sxs-lookup"><span data-stu-id="f18ae-120">You can apply almost everything you learn from working with properties to indexers.</span></span> <span data-ttu-id="f18ae-121">Jedinou výjimkou tohoto pravidla je *automaticky implementované vlastnosti*.</span><span class="sxs-lookup"><span data-stu-id="f18ae-121">The only exception to that rule is *auto implemented properties*.</span></span> <span data-ttu-id="f18ae-122">Kompilátor nemůže vždy generovat správné úložiště pro indexer.</span><span class="sxs-lookup"><span data-stu-id="f18ae-122">The compiler cannot always generate the correct storage for an indexer.</span></span>

<span data-ttu-id="f18ae-123">Přítomnost argumenty, chcete-li položku v sadě položek indexery odlišuje od vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="f18ae-123">The presence of arguments to reference an item in a set of items distinguishes indexers from properties.</span></span> <span data-ttu-id="f18ae-124">Několik indexerů může definovat podle typu, tak dlouho, dokud argument uvádí pro každý indexeru je jedinečný.</span><span class="sxs-lookup"><span data-stu-id="f18ae-124">You may define multiple indexers on a type, as long as the argument lists for each indexer is unique.</span></span> <span data-ttu-id="f18ae-125">Podíváme se různé scénáře kde můžete použít jeden nebo více indexery v definici třídy.</span><span class="sxs-lookup"><span data-stu-id="f18ae-125">Let's explore different scenarios where you might use one or more indexers in a class definition.</span></span> 

## <a name="scenarios"></a><span data-ttu-id="f18ae-126">Scénáře</span><span class="sxs-lookup"><span data-stu-id="f18ae-126">Scenarios</span></span>

<span data-ttu-id="f18ae-127">Můžete nadefinovat *indexery* v vašeho typu při jeho API modelů některé kolekce, ve které definujete argumenty, které do této kolekce.</span><span class="sxs-lookup"><span data-stu-id="f18ae-127">You would define *indexers* in your type when its API models some collection where you define the arguments to that collection.</span></span> <span data-ttu-id="f18ae-128">Vaše indexery může nebo nemusí mapovat přímo na typy kolekcí, které jsou součástí rozhraní .NET framework core.</span><span class="sxs-lookup"><span data-stu-id="f18ae-128">Your indexers may or may not map directly to the collection types that are part of the .NET core framework.</span></span> <span data-ttu-id="f18ae-129">Typ vašeho může mít jiné odpovědnosti kromě modelování kolekce.</span><span class="sxs-lookup"><span data-stu-id="f18ae-129">Your type may have other responsibilities in addition to modeling a collection.</span></span>
<span data-ttu-id="f18ae-130">Indexery umožňují poskytují rozhraní API, která odpovídá typu vašeho abstrakce bez vystavení vnitřní podrobnosti o tom, jak jsou hodnoty pro tuto abstrakci uložené či počítaný.</span><span class="sxs-lookup"><span data-stu-id="f18ae-130">Indexers enable you to provide the API that matches your type's abstraction without exposing the inner details of how the values for that abstraction are stored or computed.</span></span>

<span data-ttu-id="f18ae-131">Projděme některé z následujících běžných scénářů pro použití *indexery*.</span><span class="sxs-lookup"><span data-stu-id="f18ae-131">Let's walk through some of the common scenarios for using *indexers*.</span></span> <span data-ttu-id="f18ae-132">Dostanete [ukázkové složky pro indexery](https://github.com/dotnet/docs/tree/master/samples/csharp/indexers).</span><span class="sxs-lookup"><span data-stu-id="f18ae-132">You can access the [sample folder for indexers](https://github.com/dotnet/docs/tree/master/samples/csharp/indexers).</span></span> <span data-ttu-id="f18ae-133">Pokyny ke stažení najdete v tématu [ukázky a výukové programy](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="f18ae-133">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="arrays-and-vectors"></a><span data-ttu-id="f18ae-134">Pole a vektory</span><span class="sxs-lookup"><span data-stu-id="f18ae-134">Arrays and Vectors</span></span>

<span data-ttu-id="f18ae-135">Jednou z nejběžnějších scénářů pro vytvoření indexery je typ vašeho modelů pole nebo vektor.</span><span class="sxs-lookup"><span data-stu-id="f18ae-135">One of the most common scenarios for creating indexers is when your type models an array, or a vector.</span></span> <span data-ttu-id="f18ae-136">Můžete vytvořit indexeru seřazený seznam dat modelu.</span><span class="sxs-lookup"><span data-stu-id="f18ae-136">You can create an indexer to model an ordered list of data.</span></span> 

<span data-ttu-id="f18ae-137">Výhoda vytváření vlastní indexeru je, že můžete definovat úložiště pro tuto kolekci, aby vyhovovaly potřebám vaší.</span><span class="sxs-lookup"><span data-stu-id="f18ae-137">The advantage of creating your own indexer is that you can define the storage for that collection to suit your needs.</span></span> <span data-ttu-id="f18ae-138">Představte si situaci, kde typ vašeho modelů historická data, která je příliš velký pro načtení do paměti najednou.</span><span class="sxs-lookup"><span data-stu-id="f18ae-138">Imagine a scenario where your type models historical data that is too large to load into memory at once.</span></span> <span data-ttu-id="f18ae-139">Budete muset zavedení a uvolnění části kolekce na základě využití.</span><span class="sxs-lookup"><span data-stu-id="f18ae-139">You need to load and unload sections of the collection based on usage.</span></span> <span data-ttu-id="f18ae-140">Následující příklad modelů toto chování.</span><span class="sxs-lookup"><span data-stu-id="f18ae-140">The example following models this behavior.</span></span> <span data-ttu-id="f18ae-141">Předává sestavy na tom, kolik datových bodů neexistuje.</span><span class="sxs-lookup"><span data-stu-id="f18ae-141">It reports on how many data points exist.</span></span> <span data-ttu-id="f18ae-142">Vytváří stránky pro uložení části dat na vyžádání.</span><span class="sxs-lookup"><span data-stu-id="f18ae-142">It creates pages to hold sections of the data on demand.</span></span> <span data-ttu-id="f18ae-143">Stránky se odeberou z paměti, aby uvolnil prostor pro stránky vyžaduje novější požadavky.</span><span class="sxs-lookup"><span data-stu-id="f18ae-143">It removes pages from memory to make room for pages needed by more recent requests.</span></span>

```csharp
public class DataSamples
{
    private class Page
    {
        private readonly List<Measurements> pageData = new List<Measurements>();
        private readonly int startingIndex;
        private readonly int length;
        private bool dirty;
        private DateTime lastAccess;

        public Page(int startingIndex, int length)
        {
            this.startingIndex = startingIndex;
            this.length = length;
            lastAccess = DateTime.Now;

            // This stays as random stuff:
            var generator = new Random();
            for(int i=0; i < length; i++)
            {
                var m = new Measurements
                {
                    HiTemp = generator.Next(50, 95),
                    LoTemp = generator.Next(12, 49),
                    AirPressure = 28.0 + generator.NextDouble() * 4
                };
                pageData.Add(m);
            }
        }
        public bool HasItem(int index) =>
            ((index >= startingIndex) &&
            (index < startingIndex + length));

        public Measurements this[int index]
        {
            get
            {
                lastAccess = DateTime.Now;
                return pageData[index - startingIndex];
            }
            set
            {
                pageData[index - startingIndex] = value;
                dirty = true;
                lastAccess = DateTime.Now;
            }
        }

        public bool Dirty => dirty;
        public DateTime LastAccess => lastAccess;
    }

    private readonly int totalSize;
    private readonly List<Page> pagesInMemory = new List<Page>();

    public DataSamples(int totalSize)
    {
        this.totalSize = totalSize;
    }

    public Measurements this[int index]
    {
        get
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");

            var page = updateCachedPagesForAccess(index);
            return page[index];
        }
        set
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");
            var page = updateCachedPagesForAccess(index);

            page[index] = value;
        }
    }

    private Page updateCachedPagesForAccess(int index)
    {
        foreach (var p in pagesInMemory)
        {
            if (p.HasItem(index))
            {
                return p;
            }
        }
        var startingIndex = (index / 1000) * 1000;
        var newPage = new Page(startingIndex, 1000);
        addPageToCache(newPage);
        return newPage;
    }

    private void addPageToCache(Page p)
    {
        if (pagesInMemory.Count > 4)
        {
            // remove oldest non-dirty page:
            var oldest = pagesInMemory
                .Where(page => !page.Dirty)
                .OrderBy(page => page.LastAccess)
                .FirstOrDefault();
            // Note that this may keep more than 5 pages in memory
            // if too much is dirty
            if (oldest != null)
                pagesInMemory.Remove(oldest);
        }
        pagesInMemory.Add(p);
    }
}
```

<span data-ttu-id="f18ae-144">Můžete postupovat podle tohoto návrhu stylu pro modelování žádné řazení kolekce tam, kde je dobré důvodů, proč nenačte celá sada dat do kolekci v paměti.</span><span class="sxs-lookup"><span data-stu-id="f18ae-144">You can follow this design idiom to model any sort of collection where there are good reasons not to load the entire set of data into an in- memory collection.</span></span> <span data-ttu-id="f18ae-145">Všimněte si, že `Page` třída je privátní vnořené třídy, který není součástí veřejné rozhraní.</span><span class="sxs-lookup"><span data-stu-id="f18ae-145">Notice that the `Page` class is a private nested class that is not part of the public interface.</span></span> <span data-ttu-id="f18ae-146">Tyto podrobnosti jsou skryta všechny uživatele této třídy.</span><span class="sxs-lookup"><span data-stu-id="f18ae-146">Those details are hidden from any users of this class.</span></span>

### <a name="dictionaries"></a><span data-ttu-id="f18ae-147">slovník</span><span class="sxs-lookup"><span data-stu-id="f18ae-147">Dictionaries</span></span>

<span data-ttu-id="f18ae-148">Další z typických možností je, když potřebujete modelu slovník nebo mapy.</span><span class="sxs-lookup"><span data-stu-id="f18ae-148">Another common scenario is when you need to model a dictionary or a map.</span></span> <span data-ttu-id="f18ae-149">Tento scénář je, když typ vašeho uloží hodnoty na základě klíče, obvykle text klíče.</span><span class="sxs-lookup"><span data-stu-id="f18ae-149">This scenario is when your type stores values based on key, typically text keys.</span></span> <span data-ttu-id="f18ae-150">Tento příklad vytvoří slovník, který mapuje argumenty příkazového řádku k [lamdba výrazy](delegates-overview.md) , spravovat tyto možnosti.</span><span class="sxs-lookup"><span data-stu-id="f18ae-150">This example creates a dictionary that maps command line arguments to [lamdba expressions](delegates-overview.md) that manage those options.</span></span> <span data-ttu-id="f18ae-151">Následující příklad ukazuje dvě třídy: `ArgsActions` třídu, která mapuje možnost příkazového řádku k `Action` delegovat a `ArgsProcessor` používající `ArgsActions` provést každý `Action` když zjistí tuto možnost.</span><span class="sxs-lookup"><span data-stu-id="f18ae-151">The following example shows two classes: an `ArgsActions` class that maps a command line option to an `Action` delegate, and an `ArgsProcessor` that uses the `ArgsActions` to execute each `Action` when it encounters that option.</span></span>

```csharp
public class ArgsProcessor
{
    private readonly ArgsActions actions;

    public ArgsProcessor(ArgsActions actions)
    {
        this.actions = actions;
    }

    public void Process(string[] args)
    {
        foreach(var arg in args)
        {
            actions[arg]?.Invoke();
        }
    }

}
public class ArgsActions
{
    readonly private Dictionary<string, Action> argsActions = new Dictionary<string, Action>();

    public Action this[string s]
    {
        get
        {
            Action action;
            Action defaultAction = () => {} ;
            return argsActions.TryGetValue(s, out action) ? action : defaultAction;
        }
    }

    public void SetOption(string s, Action a)
    {
        argsActions[s] = a;
    }
}
```

<span data-ttu-id="f18ae-152">V tomto příkladu `ArgsAction` kolekce mapuje úzce zdrojové kolekce.</span><span class="sxs-lookup"><span data-stu-id="f18ae-152">In this example, the `ArgsAction` collection maps closely to the underlying collection.</span></span>
<span data-ttu-id="f18ae-153">`get` Určuje, pokud byla nakonfigurována danou možnost.</span><span class="sxs-lookup"><span data-stu-id="f18ae-153">The `get` determines if a given option has been configured.</span></span> <span data-ttu-id="f18ae-154">Pokud ano, vrátí hodnotu `Action` přidružené k této možnosti.</span><span class="sxs-lookup"><span data-stu-id="f18ae-154">If so, it returns the `Action` associated with that option.</span></span> <span data-ttu-id="f18ae-155">Pokud ne, vrátí hodnotu `Action` neprovede žádnou akci.</span><span class="sxs-lookup"><span data-stu-id="f18ae-155">If not, it returns an `Action` that does nothing.</span></span> <span data-ttu-id="f18ae-156">Veřejné přistupujícího objektu nezahrnuje `set` přistupujícího objektu.</span><span class="sxs-lookup"><span data-stu-id="f18ae-156">The public accessor does not include a `set` accessor.</span></span> <span data-ttu-id="f18ae-157">Místo toho návrhu pomocí veřejnou metodu pro nastavení možností.</span><span class="sxs-lookup"><span data-stu-id="f18ae-157">Rather, the design using a public method for setting options.</span></span>

### <a name="multi-dimensional-maps"></a><span data-ttu-id="f18ae-158">Multidimenzionální mapy</span><span class="sxs-lookup"><span data-stu-id="f18ae-158">Multi-Dimensional Maps</span></span>

<span data-ttu-id="f18ae-159">Můžete vytvořit indexery, které používají více argumentů.</span><span class="sxs-lookup"><span data-stu-id="f18ae-159">You can create indexers that use multiple arguments.</span></span> <span data-ttu-id="f18ae-160">Kromě toho tyto argumenty nejsou omezené být stejného typu.</span><span class="sxs-lookup"><span data-stu-id="f18ae-160">In addition, those arguments are not constrained to be the same type.</span></span> <span data-ttu-id="f18ae-161">Podívejme se na dva příklady.</span><span class="sxs-lookup"><span data-stu-id="f18ae-161">Let's look at two examples.</span></span>   

<span data-ttu-id="f18ae-162">První příklad ukazuje třídu, která generuje hodnoty pro sadu Mandelbrot.</span><span class="sxs-lookup"><span data-stu-id="f18ae-162">The first example shows a class that generates values for a Mandelbrot set.</span></span> <span data-ttu-id="f18ae-163">Další informace o Matematika za sadu číst [v tomto článku](https://en.wikipedia.org/wiki/Mandelbrot_set).</span><span class="sxs-lookup"><span data-stu-id="f18ae-163">For more information on the mathematics behind the set, read [this article](https://en.wikipedia.org/wiki/Mandelbrot_set).</span></span> <span data-ttu-id="f18ae-164">Indexer používá dvě hodnoty Double pro definování bod v X, Y roviny.</span><span class="sxs-lookup"><span data-stu-id="f18ae-164">The indexer uses two doubles to define a point in the X, Y plane.</span></span>
<span data-ttu-id="f18ae-165">Přistupující objekt get vypočítá počet iterací, dokud bod je určen tak, aby nebyl v sadě.</span><span class="sxs-lookup"><span data-stu-id="f18ae-165">The get accessor computes the number of iterations until a point is determined to be not in the set.</span></span> <span data-ttu-id="f18ae-166">Pokud bude dosažen maximální počet iterací, bod je v sadě a je vrácena hodnota maxIterations třídu.</span><span class="sxs-lookup"><span data-stu-id="f18ae-166">If the maximum iterations is reached, the point is in the set, and the class's maxIterations value is returned.</span></span> <span data-ttu-id="f18ae-167">(Image počítače generované popularized pro sadu Mandelbrot definovat barvy pro počet opakování je třeba určit, že bod je mimo danou sadu.</span><span class="sxs-lookup"><span data-stu-id="f18ae-167">(The computer generated images popularized for the Mandelbrot set define colors for the number of iterations necessary to determine that a point is outside the set.</span></span>

```csharp
public class Mandelbrot
{
    readonly private int maxIterations;

    public Mandelbrot(int maxIterations)
    {
        this.maxIterations = maxIterations;
    }

    public int this [double x, double y]
    {
        get
        {
            var iterations = 0;
            var x0 = x;
            var y0 = y;

            while ((x*x + y * y < 4) &&
                (iterations < maxIterations))
            {
                var newX = x * x - y * y + x0;
                y = 2 * x * y + y0;
                x = newX;
                iterations++;
            }
            return iterations;
        }
    }
}
```

<span data-ttu-id="f18ae-168">Definuje sadu Mandelbrot hodnoty v každé (x, y) koordinaci skutečných číselné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="f18ae-168">The Mandelbrot Set defines values at every (x,y) coordinate for real number values.</span></span>
<span data-ttu-id="f18ae-169">Slovník, který může obsahovat libovolný počet hodnot, který definuje.</span><span class="sxs-lookup"><span data-stu-id="f18ae-169">That defines a dictionary that could contain an infinite number of values.</span></span> <span data-ttu-id="f18ae-170">Proto neexistuje žádné úložiště za sadu.</span><span class="sxs-lookup"><span data-stu-id="f18ae-170">Therefore, there is no storage behind the set.</span></span> <span data-ttu-id="f18ae-171">Místo toho tato třída vypočítá hodnotu pro každý bod při volání kódu `get` přistupujícího objektu.</span><span class="sxs-lookup"><span data-stu-id="f18ae-171">Instead, this class computes the value for each point when code calls the `get` accessor.</span></span> <span data-ttu-id="f18ae-172">Neexistuje žádná základní úložiště použít.</span><span class="sxs-lookup"><span data-stu-id="f18ae-172">There's no underlying storage used.</span></span>

<span data-ttu-id="f18ae-173">Podívejme se na jedno použití poslední indexery, kde indexeru trvá několik argumentů různých typů.</span><span class="sxs-lookup"><span data-stu-id="f18ae-173">Let's examine one last use of indexers, where the indexer takes multiple arguments of different types.</span></span> <span data-ttu-id="f18ae-174">Vezměte v úvahu program, který spravuje teploty historická data.</span><span class="sxs-lookup"><span data-stu-id="f18ae-174">Consider a program that manages historical temperature data.</span></span> <span data-ttu-id="f18ae-175">Indexer používá města a datum nastavit nebo získat teploty vysoké a nízké pro toto umístění:</span><span class="sxs-lookup"><span data-stu-id="f18ae-175">This indexer uses a city and a date to set or get the high and low temperatures for that location:</span></span>

```csharp
using DateMeasurements = 
    System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements = 
    System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;

public class HistoricalWeatherData
{
    readonly CityDataMeasurements storage = new CityDataMeasurements();

    public Measurements this[string city, DateTime date]
    {
        get
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
                throw new ArgumentOutOfRangeException(nameof(city), "City not found");

            // strip out any time portion:
            var index = date.Date;
            var measure = default(Measurements);
            if (cityData.TryGetValue(index, out measure))
                return measure;
            throw new ArgumentOutOfRangeException(nameof(date), "Date not found");
        }
        set
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
            {
                cityData = new DateMeasurements();
                storage.Add(city, cityData);
            }

            // Strip out any time portion:
            var index = date.Date;
            cityData[index] = value;
        }
    }
}
```

<span data-ttu-id="f18ae-176">Tento příklad vytvoří indexer, který mapuje počasí data na dvou různých argumenty: Město (reprezentována `string`) a datum (reprezentována `DateTime`).</span><span class="sxs-lookup"><span data-stu-id="f18ae-176">This example creates an indexer that maps weather data on two different arguments: a city (represented by a `string`) and a date (represented by a `DateTime`).</span></span> <span data-ttu-id="f18ae-177">Interní úložiště používá dva `Dictionary` třídy představující dvourozměrná slovníku.</span><span class="sxs-lookup"><span data-stu-id="f18ae-177">The internal storage uses two `Dictionary` classes to represent the two-dimensional dictionary.</span></span> <span data-ttu-id="f18ae-178">Veřejné rozhraní API už představuje základní úložiště.</span><span class="sxs-lookup"><span data-stu-id="f18ae-178">The public API no longer represents the underlying storage.</span></span> <span data-ttu-id="f18ae-179">Místo toho funkce jazyka indexery umožňuje vytvářet veřejné rozhraní, které představuje abstrakce, i když příslušné úložiště musí používat jiný základní typy kolekcí.</span><span class="sxs-lookup"><span data-stu-id="f18ae-179">Rather, the language features of indexers enables you to create a public interface that represents your abstraction, even though the underlying storage must use different core collection types.</span></span>

<span data-ttu-id="f18ae-180">Existují dvě části tohoto kódu, který může být obeznámeni některé vývojářům.</span><span class="sxs-lookup"><span data-stu-id="f18ae-180">There are two parts of this code that may be unfamiliar to some developers.</span></span> <span data-ttu-id="f18ae-181">Tyto dva `using` příkazy:</span><span class="sxs-lookup"><span data-stu-id="f18ae-181">These two `using` statements:</span></span>

```csharp
using DateMeasurements = System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements = System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;
```

<span data-ttu-id="f18ae-182">vytvoření *alias* pro vytvořený obecného typu.</span><span class="sxs-lookup"><span data-stu-id="f18ae-182">create an *alias* for a constructed generic type.</span></span> <span data-ttu-id="f18ae-183">Tyto příkazy Povolit kód, abyste mohli používat více popisný `DateMeasurements` a `CityDateMeasurements` názvy místo obecné konstrukce `Dictionary<DateTime, Measurements>` a `Dictionary<string, Dictionary<DateTime, Measurements> >`.</span><span class="sxs-lookup"><span data-stu-id="f18ae-183">Those statements enable the code later to use the more descriptive `DateMeasurements` and `CityDateMeasurements` names instead of the generic construction of `Dictionary<DateTime, Measurements>` and `Dictionary<string, Dictionary<DateTime, Measurements> >`.</span></span> <span data-ttu-id="f18ae-184">Tento konstruktor nevyžaduje, použijte plně kvalifikovaný typ názvy na pravé straně `=` přihlášení.</span><span class="sxs-lookup"><span data-stu-id="f18ae-184">This construct does require using the fully qualified type names on the right side of the `=` sign.</span></span>

<span data-ttu-id="f18ae-185">Druhý způsob spočívá je oddělit vypnout části času každého `DateTime` objekt použitý index do kolekce.</span><span class="sxs-lookup"><span data-stu-id="f18ae-185">The second technique is to strip off the time portions of any `DateTime` object used to index into the collections.</span></span> <span data-ttu-id="f18ae-186">Rozhraní .NET framework nezahrnuje pouze typ datum.</span><span class="sxs-lookup"><span data-stu-id="f18ae-186">The .NET framework does not include a Date only type.</span></span>
<span data-ttu-id="f18ae-187">Vývojáři použít `DateTime` typu, ale použít `Date` vlastnost zajistit, aby všechny `DateTime` objekt z daný den jsou stejné.</span><span class="sxs-lookup"><span data-stu-id="f18ae-187">Developers use the `DateTime` type, but use the `Date` property to ensure that any `DateTime` object from that day are equal.</span></span>

## <a name="summing-up"></a><span data-ttu-id="f18ae-188">Shrnutí</span><span class="sxs-lookup"><span data-stu-id="f18ae-188">Summing Up</span></span>

<span data-ttu-id="f18ae-189">Měli byste vytvořit indexery, můžete kdykoli máte prvek jako vlastnost ve třídě, přičemž tuto vlastnost představuje jednu hodnotu, ale spíš kolekci hodnot, kde jednotlivé položky je identifikována sadu argumentů.</span><span class="sxs-lookup"><span data-stu-id="f18ae-189">You should create indexers anytime you have a property-like element in your class where that property represents not a single value, but rather a collection of values where each individual item is identified by a set of arguments.</span></span> <span data-ttu-id="f18ae-190">Tyto argumenty může jedinečně identifikovat, která položka v kolekci by měla odkazovat.</span><span class="sxs-lookup"><span data-stu-id="f18ae-190">Those arguments can uniquely identify which item in the collection should be referenced.</span></span>
<span data-ttu-id="f18ae-191">Indexery rozšířit koncept [vlastnosti](properties.md), kde je členem zacházet jako položku dat z mimo třídu, ale jako metody na straně.</span><span class="sxs-lookup"><span data-stu-id="f18ae-191">Indexers extend the concept of [properties](properties.md), where a member is treated like a data item from outside the class, but like a method on the side.</span></span> <span data-ttu-id="f18ae-192">Indexery povolit argumenty najít jednu položku ve vlastnosti, která představuje sadu položek.</span><span class="sxs-lookup"><span data-stu-id="f18ae-192">Indexers allow arguments to find a single item in a property that represents a set of items.</span></span>