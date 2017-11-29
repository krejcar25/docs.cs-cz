---
title: "Výpočetní výrazy (F#)"
description: "Naučte se vytvářet vhodné syntaxe pro psaní výpočtů v F #, která může být sekvencování a spojovat pomocí konstrukce toku řízení a vazeb."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: acabbf5d-fbb8-479f-894c-7251bf16c8c3
ms.openlocfilehash: 15ba2e167efc1d295d81439dcf85bc7272e05265
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="computation-expressions"></a><span data-ttu-id="9fc43-104">Výpočetní výrazy</span><span class="sxs-lookup"><span data-stu-id="9fc43-104">Computation Expressions</span></span>

<span data-ttu-id="9fc43-105">Výpočetní výrazy v jazyce F # poskytují pohodlný syntaxi pro zápis výpočtů, u kterých může být sekvencování a spojovat pomocí konstrukce toku řízení a vazeb.</span><span class="sxs-lookup"><span data-stu-id="9fc43-105">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="9fc43-106">Slouží k poskytování vhodné syntaxe pro *monads*, funkční programovací funkce, která slouží ke správě dat, řízení a vedlejší efekty při funkční programy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-106">They can be used to provide a convenient syntax for *monads*, a functional programming feature that can be used to manage data, control, and side effects in functional programs.</span></span>


## <a name="built-in-workflows"></a><span data-ttu-id="9fc43-107">Předdefinované pracovní postupy</span><span class="sxs-lookup"><span data-stu-id="9fc43-107">Built-in Workflows</span></span>
<span data-ttu-id="9fc43-108">Sekvenční výrazy jsou příkladem výpočetní výraz, jako jsou asynchronní pracovní postupy a výrazy dotazů.</span><span class="sxs-lookup"><span data-stu-id="9fc43-108">Sequence expressions are an example of a computation expression, as are asynchronous workflows and query expressions.</span></span> <span data-ttu-id="9fc43-109">Další informace najdete v tématu [pořadí](sequences.md), [asynchronní pracovní postupy](asynchronous-workflows.md), a [výrazy dotazů](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9fc43-109">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

<span data-ttu-id="9fc43-110">Některé funkce jsou společné pro sekvenční výrazy a asynchronní pracovní postupy a ilustrují, základní syntaxe pro výpočetní výraz:</span><span class="sxs-lookup"><span data-stu-id="9fc43-110">Certain features are common to both sequence expressions and asynchronous workflows and illustrate the basic syntax for a computation expression:</span></span>

```fsharp
builder-name { expression }
```

<span data-ttu-id="9fc43-111">Předchozí syntaxe Určuje, že je daný výraz výpočetní výraz typu určeného *název tvůrce*.</span><span class="sxs-lookup"><span data-stu-id="9fc43-111">The previous syntax specifies that the given expression is a computation expression of a type specified by *builder-name*.</span></span> <span data-ttu-id="9fc43-112">Výpočetní výraz může být předdefinované pracovního postupu, jako například `seq` nebo `async`, nebo může být něco definujete.</span><span class="sxs-lookup"><span data-stu-id="9fc43-112">The computation expression can be a built-in workflow, such as `seq` or `async`, or it can be something you define.</span></span> <span data-ttu-id="9fc43-113">*Název tvůrce* je identifikátor instance speciální typ označovaný jako *typu Tvůrce*.</span><span class="sxs-lookup"><span data-stu-id="9fc43-113">The *builder-name* is the identifier for an instance of a special type known as the *builder type*.</span></span> <span data-ttu-id="9fc43-114">Tvůrce typ je typ třídy, která definuje speciální metody, které řídí způsob fragmentů výpočetní výraz se zkombinují, který je kód, které řídí, jak se provádí výraz.</span><span class="sxs-lookup"><span data-stu-id="9fc43-114">The builder type is a class type that defines special methods that govern the way the fragments of the computation expression are combined, that is, code that controls how the expression executes.</span></span> <span data-ttu-id="9fc43-115">Dalším způsobem popisují třídu Tvůrce je to znamená, že umožňuje přizpůsobit operaci mnoho F # konstrukce, jako jsou smyčky a vazby.</span><span class="sxs-lookup"><span data-stu-id="9fc43-115">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

<span data-ttu-id="9fc43-116">Výpočetní výrazy je dostupná pro některé běžné jazykové konstrukty dva formuláře.</span><span class="sxs-lookup"><span data-stu-id="9fc43-116">In computation expressions, two forms are available for some common language constructs.</span></span> <span data-ttu-id="9fc43-117">Můžete vyvolat variant konstrukce pomocí!</span><span class="sxs-lookup"><span data-stu-id="9fc43-117">You can invoke the variant constructs by using a !</span></span> <span data-ttu-id="9fc43-118">(bang) přípona na určité klíčová slova, jako například `let!`, `do!`a tak dále.</span><span class="sxs-lookup"><span data-stu-id="9fc43-118">(bang) suffix on certain keywords, such as `let!`, `do!`, and so on.</span></span> <span data-ttu-id="9fc43-119">Tyto speciální formuláře způsobit, že určité funkce definovaný ve třídě Tvůrce nahradit obyčejnou předdefinované chování těchto operací.</span><span class="sxs-lookup"><span data-stu-id="9fc43-119">These special forms cause certain functions defined in the builder class to replace the ordinary built-in behavior of these operations.</span></span> <span data-ttu-id="9fc43-120">Tyto formuláře vypadat `yield!` formu `yield` klíčové slovo, které se používá v pořadí výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-120">These forms resemble the `yield!` form of the `yield` keyword that is used in sequence expressions.</span></span> <span data-ttu-id="9fc43-121">Další informace najdete v tématu [pořadí](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="9fc43-121">For more information, see [Sequences](sequences.md).</span></span>


## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="9fc43-122">Vytvoření nového typu – výpočetní výraz</span><span class="sxs-lookup"><span data-stu-id="9fc43-122">Creating a New Type of Computation Expression</span></span>
<span data-ttu-id="9fc43-123">Vytvoření třídy tvůrce a definováním některé speciální metody pro třídu můžete definovat vlastnosti vlastní výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-123">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="9fc43-124">Třída tvůrce můžete volitelně definovat metody, jak je uvedeno v následující tabulce.</span><span class="sxs-lookup"><span data-stu-id="9fc43-124">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="9fc43-125">Následující tabulka popisuje metody, které lze použít v třídě Tvůrce pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="9fc43-125">The following table describes methods that can be used in a workflow builder class.</span></span>


|<span data-ttu-id="9fc43-126">**– Metoda**</span><span class="sxs-lookup"><span data-stu-id="9fc43-126">**Method**</span></span>|<span data-ttu-id="9fc43-127">**Typické podpisy**</span><span class="sxs-lookup"><span data-stu-id="9fc43-127">**Typical signature(s)**</span></span>|<span data-ttu-id="9fc43-128">**Popis**</span><span class="sxs-lookup"><span data-stu-id="9fc43-128">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="9fc43-129">Volá se pro `let!` a `do!` v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-129">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="9fc43-130">Zabalí výpočetní výraz jako funkce.</span><span class="sxs-lookup"><span data-stu-id="9fc43-130">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="9fc43-131">Volá se pro `return` v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-131">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="9fc43-132">Volá se pro `return!` v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-132">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="9fc43-133">`M<'T> -> M<'T>`nebo</span><span class="sxs-lookup"><span data-stu-id="9fc43-133">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="9fc43-134">Spustí výpočetní výraz.</span><span class="sxs-lookup"><span data-stu-id="9fc43-134">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="9fc43-135">`M<'T> * M<'T> -> M<'T>`nebo</span><span class="sxs-lookup"><span data-stu-id="9fc43-135">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="9fc43-136">Volá se pro sekvencování v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-136">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="9fc43-137">`seq<'T> * ('T -> M<'U>) -> M<'U>`nebo</span><span class="sxs-lookup"><span data-stu-id="9fc43-137">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="9fc43-138">Volá se pro `for...do` výrazy v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-138">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="9fc43-139">Volá se pro `try...finally` výrazy v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-139">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="9fc43-140">Volá se pro `try...with` výrazy v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-140">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="9fc43-141">Volá se pro `use` vazby do ve výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-141">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="9fc43-142">Volá se pro `while...do` výrazy v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-142">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="9fc43-143">Volá se pro `yield` výrazy v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-143">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="9fc43-144">Volá se pro `yield!` výrazy v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-144">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="9fc43-145">Volá se pro prázdný `else` větví z `if...then` výrazy v výpočetní výrazy.</span><span class="sxs-lookup"><span data-stu-id="9fc43-145">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
<span data-ttu-id="9fc43-146">Mnoho z metod ve třídě Tvůrce použít a vrátit `M<'T>` konstrukce, což je většinou samostatně definovaný typ, který charakterizuje druh výpočty kombinováním, například, `Async<'T>` pro asynchronní pracovní postupy a `Seq<'T>` pořadí pracovních postupů.</span><span class="sxs-lookup"><span data-stu-id="9fc43-146">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="9fc43-147">Podpisy z těchto metod je kombinaci a vnořené mezi sebou, povolit tak, aby pracovní postup objekt vrácený jeden konstrukce můžete předat na další.</span><span class="sxs-lookup"><span data-stu-id="9fc43-147">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="9fc43-148">Kompilátor, při analýze výpočetní výraz Převede výraz na řadu vnořená volání funkcí pomocí metody v předchozí tabulce a kód v výpočetní výraz.</span><span class="sxs-lookup"><span data-stu-id="9fc43-148">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="9fc43-149">Vnořené výraz je v následujícím formátu:</span><span class="sxs-lookup"><span data-stu-id="9fc43-149">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="9fc43-150">Ve výše uvedeném kódu volání `Run` a `Delay` byly vynechány, pokud nejsou definovány ve třídě výpočetní výraz Tvůrce.</span><span class="sxs-lookup"><span data-stu-id="9fc43-150">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="9fc43-151">Tělo výpočetní výraz, zde označené jako `{| cexpr |}`, je přeložen do volání metody třídy tvůrce zahrnující překlady popsané v následující tabulce.</span><span class="sxs-lookup"><span data-stu-id="9fc43-151">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="9fc43-152">Výpočetní výraz `{| cexpr |}` je definovaný rekurzivně podle těchto překladů kde `expr` je výraz F # a `cexpr` je výpočetní výraz.</span><span class="sxs-lookup"><span data-stu-id="9fc43-152">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>



|<span data-ttu-id="9fc43-153">Výraz</span><span class="sxs-lookup"><span data-stu-id="9fc43-153">Expression</span></span>|<span data-ttu-id="9fc43-154">Překlad</span><span class="sxs-lookup"><span data-stu-id="9fc43-154">Translation</span></span>|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}<code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}<code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr), builder.Delay({&#124;cexpr &#124;})</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|
<span data-ttu-id="9fc43-155">V předchozí tabulce `other-expr` popisuje výraz, který není v opačném případě uvedené v tabulce.</span><span class="sxs-lookup"><span data-stu-id="9fc43-155">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="9fc43-156">Třída Tvůrce není nutné k implementaci všechny metody a podporovat všechny překladů uvedené v předchozí tabulce.</span><span class="sxs-lookup"><span data-stu-id="9fc43-156">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="9fc43-157">Tyto koncepty, která nejsou implementované nejsou k dispozici v výpočetní výrazy daného typu.</span><span class="sxs-lookup"><span data-stu-id="9fc43-157">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="9fc43-158">Například, pokud nechcete pro podporu `use` – klíčové slovo v výpočetní výrazy, můžete vynechat definice `Use` v třídě Tvůrce.</span><span class="sxs-lookup"><span data-stu-id="9fc43-158">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="9fc43-159">Následující příklad kódu ukazuje výpočetní výraz, který zapouzdřuje výpočet jako sérii kroků, které lze vyhodnotit jeden krok najednou.</span><span class="sxs-lookup"><span data-stu-id="9fc43-159">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="9fc43-160">Rozlišované sjednocení typ, A `OkOrException`, jak vyhodnotit dosavadní kóduje chybový stav výrazu.</span><span class="sxs-lookup"><span data-stu-id="9fc43-160">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="9fc43-161">Tento kód ukazuje několik typické vzorů, které můžete použít v výpočetní výrazy, například standardní implementace některé metody Tvůrce.</span><span class="sxs-lookup"><span data-stu-id="9fc43-161">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> NotYetDone (fun () -> func value)
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res -> 
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally 
            (whileLoop 
                (fun () -> ie.MoveNext()) 
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this 
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "NotYetDone <closure>"
comp |> step |> step |> step |> step |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step |> step |> step |> step |> step
```

<span data-ttu-id="9fc43-162">Výpočetní výraz má základní typ, který vrací výraz.</span><span class="sxs-lookup"><span data-stu-id="9fc43-162">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="9fc43-163">Základní typ může představovat výsledku počítaný nebo zpožděné výpočtu, který lze provést, nebo ho může poskytnout způsob, jak iteraci v rámci nějaký typ kolekce.</span><span class="sxs-lookup"><span data-stu-id="9fc43-163">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="9fc43-164">V předchozím příkladu základní typ byl **nakonec**.</span><span class="sxs-lookup"><span data-stu-id="9fc43-164">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="9fc43-165">Pro výraz pořadí je základní typ <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9fc43-165">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9fc43-166">Pro výraz dotazu je základní typ <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9fc43-166">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9fc43-167">Pracovním postupu asychronous je základní typ [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="9fc43-167">For an asychronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="9fc43-168">`Async` Objekt představuje pracovní provést k výpočtu výsledek.</span><span class="sxs-lookup"><span data-stu-id="9fc43-168">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="9fc43-169">Například volání [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) ke spouštění výpočet a vrátí výsledek.</span><span class="sxs-lookup"><span data-stu-id="9fc43-169">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="9fc43-170">Vlastní operace</span><span class="sxs-lookup"><span data-stu-id="9fc43-170">Custom Operations</span></span>
<span data-ttu-id="9fc43-171">Můžete definovat vlastní operaci na výpočetní výraz a použít vlastní operaci jako operátor v výpočetní výraz.</span><span class="sxs-lookup"><span data-stu-id="9fc43-171">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="9fc43-172">Operátor dotazu může obsahovat třeba ve výrazu dotazu.</span><span class="sxs-lookup"><span data-stu-id="9fc43-172">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="9fc43-173">Když definujete vlastní operace, je nutné definovat výnos a pro metody ve Výpočetní výraz.</span><span class="sxs-lookup"><span data-stu-id="9fc43-173">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="9fc43-174">Chcete-li definovat vlastní operace, umístí jej do Tvůrce třídy pro výpočetní výraz a potom použít [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span><span class="sxs-lookup"><span data-stu-id="9fc43-174">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="9fc43-175">Tento atribut přebírá řetězec jako argument, což je název, který se má použít v rámci vlastní operace.</span><span class="sxs-lookup"><span data-stu-id="9fc43-175">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="9fc43-176">Tento název se dodává do oboru na začátku otevření složené závorky výpočetní výraz.</span><span class="sxs-lookup"><span data-stu-id="9fc43-176">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="9fc43-177">Proto byste neměli používat identifikátory, které mají stejný název jako vlastní operaci v tomto bloku.</span><span class="sxs-lookup"><span data-stu-id="9fc43-177">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="9fc43-178">Například nepoužívejte identifikátorů například `all` nebo `last` ve výrazech dotazů.</span><span class="sxs-lookup"><span data-stu-id="9fc43-178">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fc43-179">Viz také</span><span class="sxs-lookup"><span data-stu-id="9fc43-179">See Also</span></span>
[<span data-ttu-id="9fc43-180">Referenční dokumentace jazyka F #</span><span class="sxs-lookup"><span data-stu-id="9fc43-180">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="9fc43-181">Asynchronní pracovní postupy</span><span class="sxs-lookup"><span data-stu-id="9fc43-181">Asynchronous Workflows</span></span>](asynchronous-workflows.md)

[<span data-ttu-id="9fc43-182">Pořadí</span><span class="sxs-lookup"><span data-stu-id="9fc43-182">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[<span data-ttu-id="9fc43-183">Výrazy dotazů</span><span class="sxs-lookup"><span data-stu-id="9fc43-183">Query Expressions</span></span>](query-expressions.md)