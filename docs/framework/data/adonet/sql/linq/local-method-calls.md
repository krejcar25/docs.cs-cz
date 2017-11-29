---
title: "Volání Local – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 32d4726924140029ebe94676f23ba5c495891e8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="local-method-calls"></a><span data-ttu-id="6d86b-102">Volání Local – metoda</span><span class="sxs-lookup"><span data-stu-id="6d86b-102">Local Method Calls</span></span>
<span data-ttu-id="6d86b-103">Volání metody místní je ten, který se spouští v objektu modelu.</span><span class="sxs-lookup"><span data-stu-id="6d86b-103">A local method call is one that is executed within the object model.</span></span> <span data-ttu-id="6d86b-104">Volání vzdálené metody je jedna, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] překládá do systému SQL a odesílá k databázovému stroji pro provedení.</span><span class="sxs-lookup"><span data-stu-id="6d86b-104">A remote method call is one that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates to SQL and transmits to the database engine for execution.</span></span> <span data-ttu-id="6d86b-105">Volání metody místní jsou potřeba při [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nemůže překládat volání do SQL.</span><span class="sxs-lookup"><span data-stu-id="6d86b-105">Local method calls are needed when [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot translate the call into SQL.</span></span> <span data-ttu-id="6d86b-106">Jinak <xref:System.InvalidOperationException> je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="6d86b-106">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="6d86b-107">Příklad 1</span><span class="sxs-lookup"><span data-stu-id="6d86b-107">Example 1</span></span>  
 <span data-ttu-id="6d86b-108">V následujícím příkladu se `Order` – třída je namapovaný k tabulce objednávky v ukázkové databázi Northwind.</span><span class="sxs-lookup"><span data-stu-id="6d86b-108">In the following example, an `Order` class is mapped to the Orders table in the Northwind sample database.</span></span> <span data-ttu-id="6d86b-109">Metoda místní instance se přidal k třídě.</span><span class="sxs-lookup"><span data-stu-id="6d86b-109">A local instance method has been added to the class.</span></span>  
  
 <span data-ttu-id="6d86b-110">V konstruktoru pro dotaz 1 `Order` třídy se spustí místně.</span><span class="sxs-lookup"><span data-stu-id="6d86b-110">In Query 1, the constructor for the `Order` class is executed locally.</span></span> <span data-ttu-id="6d86b-111">V dotazu 2, pokud [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se pokusila přeložit `LocalInstanceMethod()`do SQL, pokus selže a <xref:System.InvalidOperationException> by být vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="6d86b-111">In Query 2, if [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tried to translate `LocalInstanceMethod()`into SQL, the attempt would fail and an <xref:System.InvalidOperationException> exception would be thrown.</span></span> <span data-ttu-id="6d86b-112">Ale protože [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] poskytuje podporu pro volání metod místní, nebude dotaz2 výjimku.</span><span class="sxs-lookup"><span data-stu-id="6d86b-112">But because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides support for local method calls, Query2 will not throw an exception.</span></span>  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6d86b-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="6d86b-113">See Also</span></span>  
 [<span data-ttu-id="6d86b-114">Základní informace</span><span class="sxs-lookup"><span data-stu-id="6d86b-114">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)