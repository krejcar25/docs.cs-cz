---
title: "Postupy: použití funkce vracející skalární uživatelem definované"
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
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0788e70230fa78281d65be9eb6e0f45e58f25806
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>Postupy: použití funkce vracející skalární uživatelem definované
Můžete namapovat metodu klienta definované na třídu pro uživatelsky definované funkce pomocí <xref:System.Data.Linq.Mapping.FunctionAttribute> atribut. Všimněte si, že tělo metoda vytvoří výraz, který zachycuje záměr volání metody a předá tento výraz, který má <xref:System.Data.Linq.DataContext> pro překlad a spouštění.  
  
> [!NOTE]
>  Přímé provádění dojde pouze v případě, že je tato funkce volána mimo dotazu. Další informace najdete v tématu [postup: vložené funkce Call User-Defined](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).  
  
## <a name="example"></a>Příklad  
 Následující kód SQL představuje skalární uživatelem definované funkce vracející `ReverseCustName()`.  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 By mapování pro tento kód metodu klienta například následující:  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a>Viz také  
 [Uživatelem definované funkce](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
