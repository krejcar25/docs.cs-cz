---
title: "Řešení potíží se zprostředkovateli typů"
description: "Zjistit potenciální řešení problémů, které se nejčastěji narazit při použití zprostředkovatelů typů v jazyce F #."
keywords: "Visual f #, f #, funkční programování"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 44533045-9862-43c5-81d9-3e05157e975a
ms.openlocfilehash: 2b54454d7950dfdd6512d849fd739f505ef3317d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-type-providers"></a>Řešení potíží se zprostředkovateli typů

Toto téma popisuje a poskytuje řešení potenciální problémy, které se nejčastěji narazit při použití zprostředkovatelů typů.


## <a name="possible-problems-with-type-providers"></a>Možné problémy s zprostředkovatelů typů
Pokud dojde k potížím při práci se zprostředkovateli typu, můžete zkontrolovat v následující tabulce nejběžnější řešení.



|Problém|Navrhovaná akce|
|-------|-----------------|
|**Změny schématu**. Typ zprostředkovatele pracovní nejlepší při schématu zdroje dat je stabilní. Je-li přidat data tabulky nebo sloupce nebo provést jiné změny schéma této, typ zprostředkovatele nerozpozná automaticky tyto změny.|Vyčištění nebo znovu sestavte projekt. Vyčistěte projekt, zvolte **sestavení**, **Vyčistit** *ProjectName* v řádku nabídek. Pokud chcete projekt znovu sestavte, zvolte **sestavení**, **znovu sestavit** *ProjectName* v řádku nabídek. Tyto akce Obnovit všechny stav zprostředkovatele typu a vynutit zprostředkovatele, který se znovu připojit ke zdroji dat a získat informace o aktualizované schématu.|
|**Chyba připojení**. Adresa URL nebo připojovací řetězec je nesprávný, sítě nebo zdroj dat nebo služba není k dispozici.|Webová služba nebo služby OData můžete zkusit adresu URL v Internet Exploreru ověřte, jestli adresa URL je správná a služba není k dispozici. Pro připojovací řetězec databáze, můžete použít nástroje pro připojení dat v **Průzkumníka serveru** pro ověření, zda je platný připojovací řetězec a databáze je k dispozici. Po obnovení připojení si pak vyčistit nebo znovu sestavte projekt tak, aby zprostředkovatel typu dojde k připojení k síti.|
|**Neplatné přihlašovací údaje**. Musí mít platný oprávnění pro datový zdroj nebo webové službě.|Pro připojení SQL musí být platná pro databázi uživatelské jméno a heslo, které jsou určené v připojovací řetězec nebo konfigurační soubor. Pokud používáte ověřování systému Windows, musíte mít přístup k databázi. Správce databáze můžete určit, co oprávnění, které potřebujete pro přístup k každou databázi a každý prvek v databázi.<br /><br />Pro webovou službu nebo datové služby musí mít příslušná pověření. Většina zprostředkovatelů typů poskytují DataContext objekt, který obsahuje vlastnost přihlašovacích údajů, kterou můžete nastavit pomocí příslušné uživatelského jména a přístupový klíč.|
|**Není platná cesta**. Cesta k souboru byl neplatný.|Ověřte, zda je cesta správná a soubor existuje. Kromě toho můžete musí správně quote žádné backlashes v cestě nebo použijte typu verbatim řetězec nebo řetězec uvozené třemi uvozovkami.|

## <a name="see-also"></a>Viz také
[Zprostředkovatelé typů](index.md)
