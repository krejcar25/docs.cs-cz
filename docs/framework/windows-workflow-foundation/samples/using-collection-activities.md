---
title: "Pomocí kolekce aktivit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57c4c720e910762a303fc4987166f22960c2f03b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="using-collection-activities"></a>Pomocí kolekce aktivit
Tento příklad znázorňuje způsob použití aktivity kolekce (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601>, a <xref:System.Activities.Statements.RemoveFromCollection%601>) s třídou, která implementuje <xref:System.Collections.ICollection> rozhraní a jak vytvořit vlastní aktivity, který iteruje nad kolekcí do Vytiskněte obsah jednotlivých prvků v kolekci. Vlastní aktivity, která se nazývá `PrintCollection`, pošle tisk do konzoly nástroje členů položky kolekci s názvem `Numbers`.  
  
 Následující tabulka popisuje čtyři aktivity, které poskytují manipulaci kolekce pro pracovní postupy.  
  
|Název aktivity|Popis|  
|-------------------|-----------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|Přidá položku do kolekce.|  
|<xref:System.Activities.Statements.ClearCollection%601>|Vymaže všechny položky v kolekci|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|Vrátí `true` Pokud zadaná položka existuje v kolekci.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|Odebere položku z kolekce.|  
  
 Ukázkový soubor obsahuje dvě řešení, jeden v adresáři CodedWorkflow a dalších v adresáři DesignerWorkflow. Jejich ukázka dvěma různými způsoby použití aktivity pro stejné účely.  
  
|Řešení|Popis|Hlavní soubory|  
|-|-|-|  
|CodedWorkflow|Vzorku klientskou aplikaci, která ukazuje, jak má být vyvolán aktivity kolekce prostřednictvím kódu programu.|**PrintCollection.cs**: Pomocná aktivitu vytiskněte ke konzole každá položka v kolekci.<br /><br /> **Program.cs**: prostřednictvím kódu programu sestavení pořadí aktivity, která obsahuje řadu aktivit kolekce a provede ji.|  
|DesignerWorkflow|Vzorku klientskou aplikaci, která demonstruje použití aktivity kolekce deklarativně v Návrháři pracovních postupů.|**CollectionWorkflow.xaml**: pracovní postup vytvořený v deklarativně pomocí návrháře, který používá kolekce aktivit.<br /><br /> **PrintCollection.cs**: Pomocná aktivitu vytiskněte ke konzole každá položka v kolekci.<br /><br /> **Program.cs**: vyvolá pracovní postup popsaný v CollectionWorkflow.xaml.|  
  
 V ukázce, položka členy kolekce `Numbers` jsou vytištěné na konzole pomocí definované vlastní aktivity, názvem `PrintCollection`.  
  
#### <a name="to-use-this-sample"></a>Pro fungování této ukázky  
  
1.  Pomocí [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], otevřete soubor řešení Collection.sln.  
  
2.  Sestavte řešení, stiskněte CTRL + SHIFT + B.  
  
3.  Chcete-li spustit řešení, stiskněte CTRL + F5.  
  
> [!IMPORTANT]
>  Ukázky může být již nainstalována na váš počítač. Před pokračováním zkontrolovat na následující adresář (výchozí).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Pokud tento adresář neexistuje, přejděte na [Windows Communication Foundation (WCF) a ukázky Windows Workflow Foundation (WF) pro rozhraní .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) ke stažení všechny [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ukázky. Tato ukázka se nachází v následujícím adresáři.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`