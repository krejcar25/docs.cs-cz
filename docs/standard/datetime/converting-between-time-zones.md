---
title: "Převádění časových údajů mezi časovými pásmy"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], converting
- time zones [.NET Framework], conversions
- UTC times, converting
- converting times
- local time conversions
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ace592f973c4730bd8b6e21006c8e54aef4c695a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="converting-times-between-time-zones"></a><span data-ttu-id="c123a-102">Převádění časových údajů mezi časovými pásmy</span><span class="sxs-lookup"><span data-stu-id="c123a-102">Converting times between time zones</span></span>

<span data-ttu-id="c123a-103">Se stává stále důležité pro každou aplikaci, která funguje s daty a časy pro zpracování rozdíly mezi časová pásma.</span><span class="sxs-lookup"><span data-stu-id="c123a-103">It is becoming increasingly important for any application that works with dates and times to handle differences between time zones.</span></span> <span data-ttu-id="c123a-104">Aplikace už můžete předpokládat, že všechny časy mohou být vyjádřeny v místním čase, který čas je k dispozici <xref:System.DateTime> struktura.</span><span class="sxs-lookup"><span data-stu-id="c123a-104">An application can no longer assume that all times can be expressed in the local time, which is the time available from the <xref:System.DateTime> structure.</span></span> <span data-ttu-id="c123a-105">Webové stránky, které se zobrazí aktuální čas v části východní USA, například chybět důvěryhodnosti, aby zákazníka ve východní Asii.</span><span class="sxs-lookup"><span data-stu-id="c123a-105">For example, a Web page that displays the current time in the eastern part of the United States will lack credibility to a customer in eastern Asia.</span></span> <span data-ttu-id="c123a-106">Toto téma vysvětluje, jak převést časy z jednoho časového pásma, a také jak převést <xref:System.DateTimeOffset> hodnoty, které mají omezenou časové pásmo.</span><span class="sxs-lookup"><span data-stu-id="c123a-106">This topic explains how to convert times from one time zone to another, as well as how to convert <xref:System.DateTimeOffset> values that have limited time zone awareness.</span></span>

## <a name="converting-to-coordinated-universal-time"></a><span data-ttu-id="c123a-107">Převádění na koordinovaný světový čas</span><span class="sxs-lookup"><span data-stu-id="c123a-107">Converting to Coordinated Universal Time</span></span>

<span data-ttu-id="c123a-108">Koordinovaný světový čas (UTC) je standardní vysokou přesnost, atomic doba.</span><span class="sxs-lookup"><span data-stu-id="c123a-108">Coordinated Universal Time (UTC) is a high-precision, atomic time standard.</span></span> <span data-ttu-id="c123a-109">Časová pásma na světě jsou vyjádřené jako kladné nebo záporné posun od času UTC.</span><span class="sxs-lookup"><span data-stu-id="c123a-109">The world’s time zones are expressed as positive or negative offsets from UTC.</span></span> <span data-ttu-id="c123a-110">UTC tak poskytuje druh časových pásem volné nebo neutrální času časového pásma.</span><span class="sxs-lookup"><span data-stu-id="c123a-110">Thus, UTC provides a kind of time-zone free or time-zone neutral time.</span></span> <span data-ttu-id="c123a-111">Použití čas UTC se doporučuje, když datum a časové přenositelnost mezi počítači je důležité.</span><span class="sxs-lookup"><span data-stu-id="c123a-111">The use of UTC time is recommended when a date and time's portability across computers is important.</span></span> <span data-ttu-id="c123a-112">(Podrobnosti a ostatní osvědčené postupy, pomocí data a časy najdete v tématu [kódování osvědčených postupů pomocí data a času v rozhraní .NET Framework](http://go.microsoft.com/fwlink/?LinkId=92342).) Převod jednotlivých časových pásem na čas UTC usnadňuje porovnávání času.</span><span class="sxs-lookup"><span data-stu-id="c123a-112">(For details and other best practices using dates and times, see [Coding best practices using DateTime in the .NET Framework](http://go.microsoft.com/fwlink/?LinkId=92342).) Converting individual time zones to UTC makes time comparisons easy.</span></span>

> [!NOTE]
> <span data-ttu-id="c123a-113">Můžete také serializovat <xref:System.DateTimeOffset> struktury pro jednoznačné určení jediný bod v čase.</span><span class="sxs-lookup"><span data-stu-id="c123a-113">You can also serialize a <xref:System.DateTimeOffset> structure to unambiguously represent a single point in time.</span></span> <span data-ttu-id="c123a-114">Protože <xref:System.DateTimeOffset> objekty ukládání hodnot data a času společně s její posun od času UTC, vždy představují do konkrétního bodu v čase ve vztahu k UTC.</span><span class="sxs-lookup"><span data-stu-id="c123a-114">Because <xref:System.DateTimeOffset> objects store a date and time value along with its offset from UTC, they always represent a particular point in time in relationship to UTC.</span></span>

<span data-ttu-id="c123a-115">Nejjednodušší způsob, jak převést čas UTC je volat `static` (`Shared` v jazyce Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="c123a-115">The easiest way to convert a time to UTC is to call the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c123a-116">Přesný převod provádí metodu závisí na hodnotu `dateTime` parametru <xref:System.DateTime.Kind%2A> vlastnost, jak ukazuje následující tabulka.</span><span class="sxs-lookup"><span data-stu-id="c123a-116">The exact conversion performed by the method depends on the value of the `dateTime` parameter's <xref:System.DateTime.Kind%2A> property, as the following table shows.</span></span>

| `DateTime.Kind`            | <span data-ttu-id="c123a-117">Převod</span><span class="sxs-lookup"><span data-stu-id="c123a-117">Conversion</span></span>                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | <span data-ttu-id="c123a-118">Převede místního času na čas UTC.</span><span class="sxs-lookup"><span data-stu-id="c123a-118">Converts local time to UTC.</span></span>                                                    |
| `DateTimeKind.Unspecified` | <span data-ttu-id="c123a-119">Předpokládá `dateTime` parametr je místní čas a převede místního času na čas UTC.</span><span class="sxs-lookup"><span data-stu-id="c123a-119">Assumes the `dateTime` parameter is local time and converts local time to UTC.</span></span> |
| `DateTimeKind.Utc`         | <span data-ttu-id="c123a-120">Vrátí `dateTime` parametr beze změny.</span><span class="sxs-lookup"><span data-stu-id="c123a-120">Returns the `dateTime` parameter unchanged.</span></span>                                    |

<span data-ttu-id="c123a-121">Následující kód převede na UTC aktuálním místním časem a zobrazí výsledek do konzoly.</span><span class="sxs-lookup"><span data-stu-id="c123a-121">The following code converts the current local time to UTC and displays the result to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

> [!NOTE]
> <span data-ttu-id="c123a-122"><xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> Metoda nevrátí nutně výsledky, které jsou stejné jako <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType> a <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="c123a-122">The <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> method does not necessarily produce results that are identical to the <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType> and <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="c123a-123">Pokud systém hostitele je místní časové pásmo obsahuje více pravidel úpravy, <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> příslušné pravidlo se vztahuje na určité datum a čas.</span><span class="sxs-lookup"><span data-stu-id="c123a-123">If the host system's local time zone includes multiple adjustment rules, <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> applies the appropriate rule to a particular date and time.</span></span> <span data-ttu-id="c123a-124">Tyto dvě metody vždy použít nejnovější pravidlo úpravy.</span><span class="sxs-lookup"><span data-stu-id="c123a-124">The other two methods always apply the latest adjustment rule.</span></span>

<span data-ttu-id="c123a-125">Pokud hodnota data a času nepředstavuje UTC, nebo místního času <xref:System.DateTime.ToUniversalTime%2A> metoda vrátí pravděpodobně chybný výsledek.</span><span class="sxs-lookup"><span data-stu-id="c123a-125">If the date and time value does not represent either the local time or UTC, the <xref:System.DateTime.ToUniversalTime%2A> method will likely return an erroneous result.</span></span> <span data-ttu-id="c123a-126">Můžete však použít <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> způsobů, jak převést datum a čas ze zadaného časového pásma.</span><span class="sxs-lookup"><span data-stu-id="c123a-126">However, you can use the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> method to convert the date and time from a specified time zone.</span></span> <span data-ttu-id="c123a-127">(Další informace o načítání <xref:System.TimeZoneInfo> objekt, který reprezentuje cílové časové pásmo, najdete v části [hledání časových pásem definovaných v lokálním systému](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) Následující kód používá <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> metoda převést východní běžný čas UTC.</span><span class="sxs-lookup"><span data-stu-id="c123a-127">(For details on retrieving a <xref:System.TimeZoneInfo> object that represents the destination time zone, see [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) The following code uses the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> method to convert Eastern Standard Time to UTC.</span></span>

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

<span data-ttu-id="c123a-128">Všimněte si, že tato metoda vyvolá <xref:System.ArgumentException> Pokud <xref:System.DateTime> objektu <xref:System.DateTime.Kind%2A> vlastnost a časové pásmo neshodují.</span><span class="sxs-lookup"><span data-stu-id="c123a-128">Note that this method throws an <xref:System.ArgumentException> if the <xref:System.DateTime> object's <xref:System.DateTime.Kind%2A> property and the time zone are mismatched.</span></span> <span data-ttu-id="c123a-129">Nesoulad nastává, pokud <xref:System.DateTime.Kind%2A> vlastnost je <xref:System.DateTimeKind?displayProperty=nameWithType> ale <xref:System.TimeZoneInfo> objekt nepředstavuje místní časové pásmo, nebo pokud <xref:System.DateTime.Kind%2A> vlastnost je <xref:System.DateTimeKind?displayProperty=nameWithType> ale <xref:System.TimeZoneInfo> objekt se nerovná <xref:System.DateTimeKind?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c123a-129">A mismatch occurs if the <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind?displayProperty=nameWithType> but the <xref:System.TimeZoneInfo> object does not represent the local time zone, or if the <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind?displayProperty=nameWithType> but the <xref:System.TimeZoneInfo> object does not equal <xref:System.DateTimeKind?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="c123a-130">Všechny tyto metody trvat <xref:System.DateTime> hodnoty jako parametry a vraťte se <xref:System.DateTime> hodnotu.</span><span class="sxs-lookup"><span data-stu-id="c123a-130">All of these methods take <xref:System.DateTime> values as parameters and return a <xref:System.DateTime> value.</span></span> <span data-ttu-id="c123a-131">Pro <xref:System.DateTimeOffset> hodnoty, <xref:System.DateTimeOffset> má struktura <xref:System.DateTimeOffset.ToUniversalTime%2A> instance metoda, která převede datum a čas aktuální instance na čas UTC.</span><span class="sxs-lookup"><span data-stu-id="c123a-131">For <xref:System.DateTimeOffset> values, the <xref:System.DateTimeOffset> structure has a <xref:System.DateTimeOffset.ToUniversalTime%2A> instance method that converts the date and time of the current instance to UTC.</span></span> <span data-ttu-id="c123a-132">Následující příklad volání <xref:System.DateTimeOffset.ToUniversalTime%2A> způsobů, jak převést místní čas a dalších několikrát koordinovaný světový čas (UTC).</span><span class="sxs-lookup"><span data-stu-id="c123a-132">The following example calls the <xref:System.DateTimeOffset.ToUniversalTime%2A> method to convert a local time and several other times to Coordinated Universal Time (UTC).</span></span>

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a><span data-ttu-id="c123a-133">Převádění na určené časové pásmo UTC</span><span class="sxs-lookup"><span data-stu-id="c123a-133">Converting UTC to a designated time zone</span></span>

<span data-ttu-id="c123a-134">Převést na místní čas UTC, najdete v části "převod na místní čas UTC", který následuje dále.</span><span class="sxs-lookup"><span data-stu-id="c123a-134">To convert UTC to local time, see the "Converting UTC to Local Time" section that follows.</span></span> <span data-ttu-id="c123a-135">Chcete-li převést UTC na čas v časovém pásmu, který určíte, volejte <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="c123a-135">To convert UTC to the time in any time zone that you designate, call the <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> method.</span></span> <span data-ttu-id="c123a-136">Metoda přebírá dva parametry:</span><span class="sxs-lookup"><span data-stu-id="c123a-136">The method takes two parameters:</span></span>

* <span data-ttu-id="c123a-137">Chcete-li převést na UTC.</span><span class="sxs-lookup"><span data-stu-id="c123a-137">The UTC to convert.</span></span> <span data-ttu-id="c123a-138">Tato hodnota musí být <xref:System.DateTime> hodnotu jehož <xref:System.DateTime.Kind%2A> je nastavena na <xref:System.DateTimeKind?displayProperty=nameWithType> nebo <xref:System.DateTimeKind?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c123a-138">This must be a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is set to <xref:System.DateTimeKind?displayProperty=nameWithType> or <xref:System.DateTimeKind?displayProperty=nameWithType>.</span></span>

* <span data-ttu-id="c123a-139">Časové pásmo a převádět na UTC.</span><span class="sxs-lookup"><span data-stu-id="c123a-139">The time zone to convert the UTC to.</span></span>

<span data-ttu-id="c123a-140">Následující kód převede na čas UTC.</span><span class="sxs-lookup"><span data-stu-id="c123a-140">The following code converts UTC to Central Standard Time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a><span data-ttu-id="c123a-141">Převádění na místní čas UTC</span><span class="sxs-lookup"><span data-stu-id="c123a-141">Converting UTC to local time</span></span>

<span data-ttu-id="c123a-142">Chcete-li převést na místní čas UTC, volejte <xref:System.DateTime.ToLocalTime%2A> metodu <xref:System.DateTime> objekt, jehož čas, který chcete převést.</span><span class="sxs-lookup"><span data-stu-id="c123a-142">To convert UTC to local time, call the <xref:System.DateTime.ToLocalTime%2A> method of the <xref:System.DateTime> object whose time you want to convert.</span></span> <span data-ttu-id="c123a-143">Přesné chování metody závisí na hodnotu objektu <xref:System.DateTime.Kind%2A> vlastnost, jak ukazuje následující tabulka.</span><span class="sxs-lookup"><span data-stu-id="c123a-143">The exact behavior of the method depends on the value of the object’s <xref:System.DateTime.Kind%2A> property, as the following table shows.</span></span>

| `DateTime.Kind`            | <span data-ttu-id="c123a-144">Převod</span><span class="sxs-lookup"><span data-stu-id="c123a-144">Conversion</span></span>                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | <span data-ttu-id="c123a-145">Vrátí <xref:System.DateTime> hodnotu beze změny.</span><span class="sxs-lookup"><span data-stu-id="c123a-145">Returns the <xref:System.DateTime> value unchanged.</span></span>                                      |
| `DateTimeKind.Unspecified` | <span data-ttu-id="c123a-146">Předpokládá, že <xref:System.DateTime> hodnota a převede na UTC na místní čas UTC.</span><span class="sxs-lookup"><span data-stu-id="c123a-146">Assumes that the <xref:System.DateTime> value is UTC and converts the UTC to local time.</span></span> |
| `DateTimeKind.Utc`         | <span data-ttu-id="c123a-147">Převede <xref:System.DateTime> hodnotu na místní čas.</span><span class="sxs-lookup"><span data-stu-id="c123a-147">Converts the <xref:System.DateTime> value to local time.</span></span>                                 |

> [!NOTE]
> <span data-ttu-id="c123a-148"><xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> Metoda se chová stejně jako `DateTime.ToLocalTime` metoda.</span><span class="sxs-lookup"><span data-stu-id="c123a-148">The <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> method behaves identically to the `DateTime.ToLocalTime` method.</span></span> <span data-ttu-id="c123a-149">Trvá jeden parametr, který je hodnota, datum a čas převést.</span><span class="sxs-lookup"><span data-stu-id="c123a-149">It takes a single parameter, which is the date and time value to convert.</span></span>

<span data-ttu-id="c123a-150">Také můžete převést čas v jakékoli časovém pásmu na místní čas s použitím `static` (`Shared` v jazyce Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="c123a-150">You can also convert the time in any designated time zone to local time by using the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c123a-151">Tato technika je popsána v další části.</span><span class="sxs-lookup"><span data-stu-id="c123a-151">This technique is discussed in the next section.</span></span>

## <a name="converting-between-any-two-time-zones"></a><span data-ttu-id="c123a-152">Převádění mezi každými dvěma časovými pásmy</span><span class="sxs-lookup"><span data-stu-id="c123a-152">Converting between any two time zones</span></span>

<span data-ttu-id="c123a-153">Můžete převádět mezi dvěma časovými pásmy pomocí některé z následujících dvou `static` (`Shared` v jazyce Visual Basic) metody <xref:System.TimeZoneInfo> třídy:</span><span class="sxs-lookup"><span data-stu-id="c123a-153">You can convert between any two time zones by using either of the following two `static` (`Shared` in Visual Basic) methods of the <xref:System.TimeZoneInfo> class:</span></span>

* <xref:System.TimeZoneInfo.ConvertTime%2A>

  <span data-ttu-id="c123a-154">Tato metoda parametry jsou hodnoty data a času, které chcete převést, `TimeZoneInfo` objekt, který reprezentuje časové pásmo hodnoty data a času a `TimeZoneInfo` objekt, který reprezentuje časové pásmo na převést na hodnotu data a času.</span><span class="sxs-lookup"><span data-stu-id="c123a-154">This method's parameters are the date and time value to convert, a `TimeZoneInfo` object that represents the time zone of the date and time value, and a `TimeZoneInfo` object that represents the time zone to convert the date and time value to.</span></span>

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  <span data-ttu-id="c123a-155">Tato metoda parametry jsou datum a čas hodnotu převést, identifikátor datum a čas hodnota časové pásmo a identifikátor časového pásma převést na hodnotu data a času.</span><span class="sxs-lookup"><span data-stu-id="c123a-155">This method's parameters are the date and time value to convert, the identifier of the date and time value's time zone, and the identifier of the time zone to convert the date and time value to.</span></span>

<span data-ttu-id="c123a-156">Obě metody vyžadují, aby <xref:System.DateTime.Kind%2A> vlastnost hodnota data a času pro převod a <xref:System.TimeZoneInfo> objektu nebo identifikátor, který představuje jeho časové pásmo odpovídají na sebe navzájem.</span><span class="sxs-lookup"><span data-stu-id="c123a-156">Both methods require that the <xref:System.DateTime.Kind%2A> property of the date and time value to convert and the <xref:System.TimeZoneInfo> object or time zone identifier that represents its time zone correspond to one another.</span></span> <span data-ttu-id="c123a-157">Jinak <xref:System.ArgumentException> je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="c123a-157">Otherwise, an <xref:System.ArgumentException> is thrown.</span></span> <span data-ttu-id="c123a-158">Například pokud `Kind` vlastnost hodnota data a času je `DateTimeKind.Local`, je vyvolána výjimka, pokud `TimeZoneInfo` objekt jako parametr předaný metodě není rovno `TimeZoneInfo.Local`.</span><span class="sxs-lookup"><span data-stu-id="c123a-158">For example, if the `Kind` property of the date and time value is `DateTimeKind.Local`, an exception is thrown if the `TimeZoneInfo` object passed as a parameter to the method is not equal to `TimeZoneInfo.Local`.</span></span> <span data-ttu-id="c123a-159">Pokud není rovno identifikátor jako parametr předaný metodě je také vyvolána výjimka `TimeZoneInfo.Local.Id`.</span><span class="sxs-lookup"><span data-stu-id="c123a-159">An exception is also thrown if the identifier passed as a parameter to the method is not equal to `TimeZoneInfo.Local.Id`.</span></span>

<span data-ttu-id="c123a-160">Následující příklad používá <xref:System.TimeZoneInfo.ConvertTime%2A> způsobů, jak převést z havajského standardního času na místní čas.</span><span class="sxs-lookup"><span data-stu-id="c123a-160">The following example uses the <xref:System.TimeZoneInfo.ConvertTime%2A> method to convert from Hawaiian Standard Time to local time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a><span data-ttu-id="c123a-161">Převádění hodnot DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="c123a-161">Converting DateTimeOffset values</span></span>

<span data-ttu-id="c123a-162">Hodnoty data a času reprezentována <xref:System.DateTimeOffset> objekty nejsou plně časových pásem vědět, protože objekt je oddělen od svého časového pásma v době, kdy je vytvořen.</span><span class="sxs-lookup"><span data-stu-id="c123a-162">Date and time values represented by <xref:System.DateTimeOffset> objects are not fully time-zone aware because the object is disassociated from its time zone at the time it is instantiated.</span></span> <span data-ttu-id="c123a-163">Ale v mnoha případech aplikace jednoduše převést datum a čas na základě na dvou různých posun od času UTC místo v době na konkrétní časová pásma.</span><span class="sxs-lookup"><span data-stu-id="c123a-163">However, in many cases an application simply needs to convert a date and time based on two different offsets from UTC rather than on the time in particular time zones.</span></span> <span data-ttu-id="c123a-164">Chcete-li provést tento převod, můžete zavolat aktuální instance <xref:System.DateTimeOffset.ToOffset%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="c123a-164">To perform this conversion, you can call the current instance's <xref:System.DateTimeOffset.ToOffset%2A> method.</span></span> <span data-ttu-id="c123a-165">Jeden parametr metody je posun nové datum a čas hodnotu, která metoda se má vrátit.</span><span class="sxs-lookup"><span data-stu-id="c123a-165">The method's single parameter is the offset of the new date and time value that the method is to return.</span></span>

<span data-ttu-id="c123a-166">Například v případě požadavku na datum a čas uživatele pro webové stránky je známý a serializován jako řetězec ve formátu MM/dd/rrrr hh: mm: zzzz, následující `ReturnTimeOnServer` metoda převede tuto hodnotu data a času na datum a čas na webovém serveru.</span><span class="sxs-lookup"><span data-stu-id="c123a-166">For example, if the date and time of a user request for a Web page is known and is serialized as a string in the format MM/dd/yyyy hh:mm:ss zzzz, the following `ReturnTimeOnServer` method converts this date and time value to the date and time on the Web server.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

<span data-ttu-id="c123a-167">Pokud metoda je předán řetězec "9/1/2007 5:32:07 -05:00", která představuje datum a čas v časovém pásmu pět hodin dříve než čas UTC, vrátí 9/1/2007 3:32:07: 00 -07:00 pro server nachází v USA Tichomořském časovém pásmu.</span><span class="sxs-lookup"><span data-stu-id="c123a-167">If the method is passed the string "9/1/2007 5:32:07 -05:00", which represents the date and time in a time zone five hours earlier than UTC, it returns 9/1/2007 3:32:07 AM -07:00 for a server located in the U.S. Pacific Standard Time zone.</span></span>

<span data-ttu-id="c123a-168"><xref:System.TimeZoneInfo> Třída také obsahuje přetížení <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> metoda, která provádí převody časové pásmo s <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> hodnoty.</span><span class="sxs-lookup"><span data-stu-id="c123a-168">The <xref:System.TimeZoneInfo> class also includes an overload of the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method that performs time zone conversions with <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> values.</span></span> <span data-ttu-id="c123a-169">Parametry metody jsou <xref:System.DateTimeOffset> hodnota a odkaz na časové pásmo, na které má být převeden čas.</span><span class="sxs-lookup"><span data-stu-id="c123a-169">The method's parameters are a <xref:System.DateTimeOffset> value and a reference to the time zone to which the time is to be converted.</span></span> <span data-ttu-id="c123a-170">Volání metody vrátí <xref:System.DateTimeOffset> hodnotu.</span><span class="sxs-lookup"><span data-stu-id="c123a-170">The method call returns a <xref:System.DateTimeOffset> value.</span></span> <span data-ttu-id="c123a-171">Například `ReturnTimeOnServer` metoda v předchozím příkladu může být přepsána takto pro volání <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> metoda.</span><span class="sxs-lookup"><span data-stu-id="c123a-171">For example, the `ReturnTimeOnServer` method in the previous example could be rewritten as follows to call the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> method.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a><span data-ttu-id="c123a-172">Viz také</span><span class="sxs-lookup"><span data-stu-id="c123a-172">See also</span></span>

<span data-ttu-id="c123a-173"><xref:System.TimeZoneInfo>[Data, časy a časová pásma](../../../docs/standard/datetime/index.md)
[hledání časových pásem definovaných v lokálním systému](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)</span><span class="sxs-lookup"><span data-stu-id="c123a-173"><xref:System.TimeZoneInfo> [Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)</span></span>