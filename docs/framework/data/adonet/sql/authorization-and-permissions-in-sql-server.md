---
title: "Autorizace a oprávnění v systému SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d340405c-91f4-4837-a3cc-a238ee89888a
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0916ca83cae40d1deda2e1126fd7b7ebab46a23c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="authorization-and-permissions-in-sql-server"></a><span data-ttu-id="bfbc4-102">Autorizace a oprávnění v systému SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfbc4-102">Authorization and Permissions in SQL Server</span></span>
<span data-ttu-id="bfbc4-103">Při vytváření databázových objektů, je třeba explicitně udělit oprávnění, aby byly dostupné pro uživatele.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-103">When you create database objects, you must explicitly grant permissions to make them accessible to users.</span></span> <span data-ttu-id="bfbc4-104">Všechny zabezpečitelné objekty má oprávnění, která lze udělit oprávnění příkazy using objekt zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-104">Every securable object has permissions that can be granted to a principal using permission statements.</span></span>  
  
## <a name="the-principle-of-least-privilege"></a><span data-ttu-id="bfbc4-105">Princip nejnižších nutných oprávnění</span><span class="sxs-lookup"><span data-stu-id="bfbc4-105">The Principle of Least Privilege</span></span>  
 <span data-ttu-id="bfbc4-106">Vývoj aplikace pomocí přístup účtu (LUA) nejmenší privilegovaných uživatelů je důležitou součástí strategie Obranným, podrobný pro zamezením bezpečnostní hrozby.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-106">Developing an application using a least-privileged user account (LUA) approach is an important part of a defensive, in-depth strategy for countering security threats.</span></span> <span data-ttu-id="bfbc4-107">LUA přístup zajišťuje, že uživatelé použijte Princip nejnižších nutných oprávnění a vždy se přihlásit s omezenou uživatelské účty.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-107">The LUA approach ensures that users follow the principle of least privilege and always log on with limited user accounts.</span></span> <span data-ttu-id="bfbc4-108">Úlohy správy jsou rozdělená za použití role pevného serveru a použití `sysadmin` pevné role serveru je vážně s omezeným přístupem.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-108">Administrative tasks are broken out using fixed server roles, and the use of the `sysadmin` fixed server role is severely restricted.</span></span>  
  
 <span data-ttu-id="bfbc4-109">Vždy použijte Princip nejnižších nutných oprávnění při udělování oprávnění uživatelům databáze.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-109">Always follow the principle of least privilege when granting permissions to database users.</span></span> <span data-ttu-id="bfbc4-110">Přidělte minimální oprávnění potřebná pro uživatele nebo roli na dané úloze.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-110">Grant the minimum permissions necessary to a user or role to accomplish a given task.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bfbc4-111">Vývoj a testování aplikace pomocí LUA přístup přidá určitý stupeň potíže při procesu vývoje.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-111">Developing and testing an application using the LUA approach adds a degree of difficulty to the development process.</span></span> <span data-ttu-id="bfbc4-112">Je snazší vytvářet objekty a napsat kód, když jste přihlášení jako správce systému nebo vlastníka databáze, než je používá účet LUA.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-112">It is easier to create objects and write code while logged on as a system administrator or database owner than it is using a LUA account.</span></span> <span data-ttu-id="bfbc4-113">Vývoj aplikací pomocí účtu s vysokými oprávněními ale obfuskováním dopad omezené funkčnosti při nejnižšími oprávněními uživatelé pokusí spustit aplikaci, která vyžaduje zvýšená oprávnění, aby bylo možné správně fungovat.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-113">However, developing applications using a highly privileged account can obfuscate the impact of reduced functionality when least privileged users attempt to run an application that requires elevated permissions in order to function correctly.</span></span> <span data-ttu-id="bfbc4-114">Udělení oprávnění nadměrné uživatelům, aby bylo možné znovu načíst ztraceny funkce můžete ponechat, vaše aplikace bude zranitelný vůči útoku.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-114">Granting excessive permissions to users in order to reacquire lost functionality can leave your application vulnerable to attack.</span></span> <span data-ttu-id="bfbc4-115">Navrhování, vývoj a testování aplikace s přihlášení s účtem LUA vynucuje určených přístup k plánování zabezpečení, který eliminuje nepříjemným výskyt nečekaných událostí a riziko jako rychlou opravu udělit oprávnění vyšší úrovně.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-115">Designing, developing and testing your application logged on with a LUA account enforces a disciplined approach to security planning that eliminates unpleasant surprises and the temptation to grant elevated privileges as a quick fix.</span></span> <span data-ttu-id="bfbc4-116">Přihlášení systému SQL Server můžete použít pro testování i v případě, že aplikace je určený k nasazení pomocí ověřování systému Windows.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-116">You can use a SQL Server login for testing even if your application is intended to deploy using Windows authentication.</span></span>  
  
## <a name="role-based-permissions"></a><span data-ttu-id="bfbc4-117">Oprávnění na základě rolí</span><span class="sxs-lookup"><span data-stu-id="bfbc4-117">Role-Based Permissions</span></span>  
 <span data-ttu-id="bfbc4-118">Udělení oprávnění k rolím a nikoli na uživatele zjednodušuje správu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-118">Granting permissions to roles rather than to users simplifies security administration.</span></span> <span data-ttu-id="bfbc4-119">Sady oprávnění, které jsou přiřazeny k rolím jsou zdědí všechny členy role.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-119">Permission sets that are assigned to roles are inherited by all members of the role.</span></span> <span data-ttu-id="bfbc4-120">Aby bylo jednodušší přidávat nebo odebírat uživatele z role, než je znovu vytvořit samostatné oprávnění nastaví pro jednotlivé uživatele.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-120">It is easier to add or remove users from a role than it is to recreate separate permission sets for individual users.</span></span> <span data-ttu-id="bfbc4-121">Role mohou být vnořené; příliš mnoho úrovní vnoření však může snížit výkon.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-121">Roles can be nested; however, too many levels of nesting can degrade performance.</span></span> <span data-ttu-id="bfbc4-122">Můžete také přidat uživatele do pevné databázové role pro zjednodušení přiřazení oprávnění.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-122">You can also add users to fixed database roles to simplify assigning permissions.</span></span>  
  
 <span data-ttu-id="bfbc4-123">Můžete udělit oprávnění na úrovni schématu.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-123">You can grant permissions at the schema level.</span></span> <span data-ttu-id="bfbc4-124">Uživatelé automaticky zdědí oprávnění na všechny nové objekty vytvořené ve schématu; není nutné udělit oprávnění, jako jsou vytvořit nové objekty.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-124">Users automatically inherit permissions on all new objects created in the schema; you do not need to grant permissions as new objects are created.</span></span>  
  
## <a name="permissions-through-procedural-code"></a><span data-ttu-id="bfbc4-125">Oprávnění prostřednictvím procedurální kódu</span><span class="sxs-lookup"><span data-stu-id="bfbc4-125">Permissions Through Procedural Code</span></span>  
 <span data-ttu-id="bfbc4-126">Zapouzdření přístup k datům prostřednictvím modulů, jako uložené procedury a uživatelem definované funkce poskytuje další úroveň ochrany okolo vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-126">Encapsulating data access through modules such as stored procedures and user-defined functions provides an additional layer of protection around your application.</span></span> <span data-ttu-id="bfbc4-127">Uživatelům můžete zabránit přímo interakci s objekty databáze tak, že udělíte oprávnění jenom na uložené procedury nebo funkce při odepření oprávnění základní objektů, jako jsou tabulky.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-127">You can prevent users from directly interacting with database objects by granting permissions only to stored procedures or functions while denying permissions to underlying objects such as tables.</span></span> <span data-ttu-id="bfbc4-128">SQL Server dosahuje pomocí řetězení vlastnictví.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-128">SQL Server achieves this by ownership chaining.</span></span>  
  
## <a name="permission-statements"></a><span data-ttu-id="bfbc4-129">Oprávnění – příkazy</span><span class="sxs-lookup"><span data-stu-id="bfbc4-129">Permission Statements</span></span>  
 <span data-ttu-id="bfbc4-130">Tři příkazy jazyka Transact-SQL oprávnění jsou popsané v následující tabulce.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-130">The three Transact-SQL permission statements are described in the following table.</span></span>  
  
|<span data-ttu-id="bfbc4-131">Příkaz oprávnění</span><span class="sxs-lookup"><span data-stu-id="bfbc4-131">Permission Statement</span></span>|<span data-ttu-id="bfbc4-132">Popis</span><span class="sxs-lookup"><span data-stu-id="bfbc4-132">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="bfbc4-133">UDĚLENÍ</span><span class="sxs-lookup"><span data-stu-id="bfbc4-133">GRANT</span></span>|<span data-ttu-id="bfbc4-134">Uděluje oprávnění.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-134">Grants a permission.</span></span>|  
|<span data-ttu-id="bfbc4-135">ODVOLÁNÍ.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-135">REVOKE</span></span>|<span data-ttu-id="bfbc4-136">Odvolá oprávnění.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-136">Revokes a permission.</span></span> <span data-ttu-id="bfbc4-137">Toto je výchozí stav nového objektu.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-137">This is the default state of a new object.</span></span> <span data-ttu-id="bfbc4-138">Oprávnění odvolává pro uživatele nebo roli stále možné zdědit z jiné skupiny nebo role, ke kterým je přiřazen k objektu zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-138">A permission revoked from a user or role can still be inherited from other groups or roles to which the principal is assigned.</span></span>|  
|<span data-ttu-id="bfbc4-139">ODEPŘÍT</span><span class="sxs-lookup"><span data-stu-id="bfbc4-139">DENY</span></span>|<span data-ttu-id="bfbc4-140">ODEPŘÍT odvolá oprávnění tak, aby nelze zdědit.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-140">DENY revokes a permission so that it cannot be inherited.</span></span> <span data-ttu-id="bfbc4-141">ODEPŘÍT má přednost před všechna oprávnění, kromě ODEPŘÍT se nevztahuje na objekt vlastníky nebo členové `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-141">DENY takes precedence over all permissions, except DENY does not apply to object owners or members of `sysadmin`.</span></span> <span data-ttu-id="bfbc4-142">Pokud ODEPŘETE oprávnění na objekt tak, aby `public` role pro všechny uživatele a role kromě vlastníky objektu se nezdařilo a `sysadmin` členy.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-142">If you DENY permissions on an object to the `public` role it is denied to all users and roles except for object owners and `sysadmin` members.</span></span>|  
  
-   <span data-ttu-id="bfbc4-143">Příkaz GRANT můžete přiřadit oprávnění do skupiny nebo role, která může být zděděn uživatele databáze.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-143">The GRANT statement can assign permissions to a group or role that can be inherited by database users.</span></span> <span data-ttu-id="bfbc4-144">ODEPŘÍT příkaz však má přednost před jiné příkazy oprávnění.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-144">However, the DENY statement takes precedence over all other permission statements.</span></span> <span data-ttu-id="bfbc4-145">Proto uživatel, který bylo odepřeno oprávnění nemůže Zdědit ji z jiné role.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-145">Therefore, a user who has been denied a permission cannot inherit it from another role.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfbc4-146">Členové `sysadmin` role a objekt vlastníků pevného serveru nemůže být odepřeno oprávnění.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-146">Members of the `sysadmin` fixed server role and object owners cannot be denied permissions.</span></span>  
  
## <a name="ownership-chains"></a><span data-ttu-id="bfbc4-147">Vlastnictví řetězů</span><span class="sxs-lookup"><span data-stu-id="bfbc4-147">Ownership Chains</span></span>  
 <span data-ttu-id="bfbc4-148">SQL Server zajišťuje, aby pouze objekty, které bylo uděleno oprávnění, můžete přístup k objekty.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-148">SQL Server ensures that only principals that have been granted permission can access objects.</span></span> <span data-ttu-id="bfbc4-149">Pokud více objektů v databázi přístup k sobě navzájem, sekvenci se označuje jako řetězec.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-149">When multiple database objects access each other, the sequence is known as a chain.</span></span> <span data-ttu-id="bfbc4-150">Když na odkazy v řetězu prochází přes SQL Server, vyhodnotí oprávnění jinak než kdyby měla přístup každou položku samostatně.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-150">When SQL Server is traversing the links in the chain, it evaluates permissions differently than it would if it were accessing each item separately.</span></span> <span data-ttu-id="bfbc4-151">Při přístupu k objektu prostřednictvím řetěz, SQL Server nejprve porovnává vlastníka objektu vlastníka objektu volání (předchozí odkaz v řetězci).</span><span class="sxs-lookup"><span data-stu-id="bfbc4-151">When an object is accessed through a chain, SQL Server first compares the object's owner to the owner of the calling object (the previous link in the chain).</span></span> <span data-ttu-id="bfbc4-152">Pokud oba objekty mají stejného vlastníka, nejsou zkontrolovat oprávnění na odkazovaného objektu.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-152">If both objects have the same owner, permissions on the referenced object are not checked.</span></span> <span data-ttu-id="bfbc4-153">Vždy, když objekt získá přístup k dalším objektem, který má jiného vlastníka, je porušený řetězec vlastnictví a SQL Server musí zkontrolujte kontext zabezpečení volajícího.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-153">Whenever an object accesses another object that has a different owner, the ownership chain is broken and SQL Server must check the caller's security context.</span></span>  
  
## <a name="procedural-code-and-ownership-chaining"></a><span data-ttu-id="bfbc4-154">Příklady kódu a vlastnictví řetězení</span><span class="sxs-lookup"><span data-stu-id="bfbc4-154">Procedural Code and Ownership Chaining</span></span>  
 <span data-ttu-id="bfbc4-155">Předpokládejme, že je uživateli uděleno oprávnění ke spouštění na uložené procedury, která vybere položku dat z tabulky.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-155">Suppose that a user is granted execute permissions on a stored procedure that selects data from a table.</span></span> <span data-ttu-id="bfbc4-156">Pokud tabulky a uložené procedury stejného vlastníka, uživatel nemusí být udělena všechna oprávnění v tabulce a můžete i odepřel oprávnění.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-156">If the stored procedure and the table have the same owner, the user doesn't need to be granted any permissions on the table and can even be denied permissions.</span></span> <span data-ttu-id="bfbc4-157">Však musí SQL Server Pokud tabulky a uložené procedury mít různé vlastníky, zkontrolujte oprávnění uživatele v tabulce před povolením přístupu k datům.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-157">However, if the stored procedure and the table have different owners, SQL Server must check the user's permissions on the table before allowing access to the data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfbc4-158">Řetězení vlastnictví neplatí v případě dynamických příkazů SQL.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-158">Ownership chaining does not apply in the case of dynamic SQL statements.</span></span> <span data-ttu-id="bfbc4-159">K volání procedury, která provede příkaz SQL, volající musí mít uděleno oprávnění pro základní tabulky, a aplikace bude zranitelný vůči útoku Injektáž SQL.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-159">To call a procedure that executes an SQL statement, the caller must be granted permissions on the underlying tables, leaving your application vulnerable to SQL Injection attack.</span></span> <span data-ttu-id="bfbc4-160">SQL Server poskytuje nové mechanismů, například zosobnění a podepisování modulů s certifikáty, které nevyžadují udělení oprávnění pro základní tabulky.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-160">SQL Server provides new mechanisms, such as impersonation and signing modules with certificates, that do not require granting permissions on the underlying tables.</span></span> <span data-ttu-id="bfbc4-161">Ty můžete použít taky s CLR uložené procedury.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-161">These can also be used with CLR stored procedures.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="bfbc4-162">Externí zdroje</span><span class="sxs-lookup"><span data-stu-id="bfbc4-162">External Resources</span></span>  
 <span data-ttu-id="bfbc4-163">Další informace najdete v následujících zdrojích informací.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-163">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="bfbc4-164">Prostředek</span><span class="sxs-lookup"><span data-stu-id="bfbc4-164">Resource</span></span>|<span data-ttu-id="bfbc4-165">Popis</span><span class="sxs-lookup"><span data-stu-id="bfbc4-165">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="bfbc4-166">[Oprávnění](http://msdn.microsoft.com/library/ms191291.aspx) v Online knihách serveru SQL</span><span class="sxs-lookup"><span data-stu-id="bfbc4-166">[Permissions](http://msdn.microsoft.com/library/ms191291.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="bfbc4-167">Obsahuje témata s popisem oprávnění hierarchie, zobrazení katalogu a oprávnění pevné role serveru a databáze.</span><span class="sxs-lookup"><span data-stu-id="bfbc4-167">Contains topics describing permissions hierarchy, catalog views, and permissions of fixed server and database roles.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfbc4-168">Viz také</span><span class="sxs-lookup"><span data-stu-id="bfbc4-168">See Also</span></span>  
 [<span data-ttu-id="bfbc4-169">Zabezpečení aplikací ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bfbc4-169">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="bfbc4-170">Scénáře zabezpečení aplikací v systému SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfbc4-170">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="bfbc4-171">Ověřování v systému SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfbc4-171">Authentication in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [<span data-ttu-id="bfbc4-172">Server a databázových rolí v systému SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfbc4-172">Server and Database Roles in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 [<span data-ttu-id="bfbc4-173">Vlastnictví a oddělení schéma uživatele v systému SQL Server</span><span class="sxs-lookup"><span data-stu-id="bfbc4-173">Ownership and User-Schema Separation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 [<span data-ttu-id="bfbc4-174">ADO.NET spravované zprostředkovatelé a středisku pro vývojáře datové sady</span><span class="sxs-lookup"><span data-stu-id="bfbc4-174">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)