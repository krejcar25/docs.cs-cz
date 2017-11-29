---
title: "ICorProfilerCallback6::GetAssemblyReferences – metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3682f40c9c49ea15ac9f084b6d5db274bfcaa8d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="64134-102">ICorProfilerCallback6::GetAssemblyReferences – metoda</span><span class="sxs-lookup"><span data-stu-id="64134-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>
<span data-ttu-id="64134-103">[Podporované v rozhraní .NET Framework 4.5.2 a novějších verzích]</span><span class="sxs-lookup"><span data-stu-id="64134-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="64134-104">Upozorní profileru, že sestavení v velmi brzy načítá fáze, když modul common language runtime provede procházení uzavření odkaz na sestavení.</span><span class="sxs-lookup"><span data-stu-id="64134-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64134-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="64134-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64134-106">Parametry</span><span class="sxs-lookup"><span data-stu-id="64134-106">Parameters</span></span>  
 `wszAssemblyPath`  
 <span data-ttu-id="64134-107">[v] Cesta a název sestavení, jejichž metadata budou upraveny.</span><span class="sxs-lookup"><span data-stu-id="64134-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="64134-108">[v] Ukazatel na adresu [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) rozhraní, které určuje sestavení odkazuje na Přidat.</span><span class="sxs-lookup"><span data-stu-id="64134-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64134-109">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="64134-109">Return Value</span></span>  
 <span data-ttu-id="64134-110">Návratové hodnoty z této zpětné volání se ignorují.</span><span class="sxs-lookup"><span data-stu-id="64134-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64134-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="64134-111">Remarks</span></span>  
 <span data-ttu-id="64134-112">Tato zpětné volání je řízena nastavením [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) příznak maska událostí při volání metody [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="64134-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="64134-113">Pokud profileru zaregistruje [icorprofilercallback6::getassemblyreferences –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) metoda zpětného volání, modul runtime předá cestu a název sestavení, která má být načten, spolu s odkazy [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) rozhraní objektu do dané metody.</span><span class="sxs-lookup"><span data-stu-id="64134-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="64134-114">Potom můžete volat profileru [icorprofilerassemblyreferenceprovider::addassemblyreference –](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) metoda s `COR_PRF_ASSEMBLY_REFERENCE_INFO` objekt pro každý cíl sestavení se plánuje odkazovat z sestavení zadané v `GetAssemblyReferences` zpětné volání.</span><span class="sxs-lookup"><span data-stu-id="64134-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="64134-115">Použití `GetAssemblyReferences` zpětného volání pouze v případě, že má profileru ke změně metadat sestavení přidat odkazy na sestavení.</span><span class="sxs-lookup"><span data-stu-id="64134-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="64134-116">(Všimněte si, že skutečné úpravy sestavení metadat se provádí v, ale [icorprofilercallback::moduleloadfinished –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)metoda zpětného volání.) Profileru by měla implementovat `GetAssemblyReferences` metoda zpětného volání k informování common language runtime (CLR), odkazy na sestavení bude přidáno, jakmile se načetl modul.</span><span class="sxs-lookup"><span data-stu-id="64134-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="64134-117">To pomáhá zajistit, že sestavení sdílení rozhodnutí CLR během této fáze časná dál platné i když profileru plánuje později upravit odkazy na metadata sestavení.</span><span class="sxs-lookup"><span data-stu-id="64134-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="64134-118">To se můžete vyhnout některých případech, ve které profileru způsobit změny metadata `SECURITY_E_INCOMPATIBLE_SHARE` chyby.</span><span class="sxs-lookup"><span data-stu-id="64134-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="64134-119">Používá profileru [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) objekt Poskytnutý tuto metodu za účelem přidání odkazů na sestavení pro uzavření walkera CLR sestavení odkaz.</span><span class="sxs-lookup"><span data-stu-id="64134-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="64134-120">[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) objekt by měl použít pouze v rámci této zpětného volání.</span><span class="sxs-lookup"><span data-stu-id="64134-120">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="64134-121">Volání [icorprofilerassemblyreferenceprovider::addassemblyreference –](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) metoda z této zpětného volání nezpůsobují v upravené metadata, ale jenom v procházení uzavření odkaz upravené sestavení.</span><span class="sxs-lookup"><span data-stu-id="64134-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="64134-122">Profileru bude muset nadále používat [imetadataassemblyemit –](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) objekt, který chcete explicitně přidat odkazy na sestavení z uvnitř [icorprofilercallback::moduleloadfinished –](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) zpětné volání pro odkazujícího sestavení, i když se implementuje `GetAssemblyReferences` zpětného volání.</span><span class="sxs-lookup"><span data-stu-id="64134-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="64134-123">Profileru musí být připravené pro příjem duplicitní volání této zpětného volání pro stejného sestavení a má odpovědět stejně jako pro každé takové duplicitní volání (tím, že stejnou sadu [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) volání).</span><span class="sxs-lookup"><span data-stu-id="64134-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64134-124">Požadavky</span><span class="sxs-lookup"><span data-stu-id="64134-124">Requirements</span></span>  
 <span data-ttu-id="64134-125">**Platformy:** najdete v části [požadavky na systém](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64134-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64134-126">**Záhlaví:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="64134-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="64134-127">**Knihovna:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64134-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64134-128">**Verze rozhraní .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64134-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64134-129">Viz také</span><span class="sxs-lookup"><span data-stu-id="64134-129">See Also</span></span>  
 [<span data-ttu-id="64134-130">Rozhraní ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="64134-130">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 [<span data-ttu-id="64134-131">Moduleloadfinished – metoda</span><span class="sxs-lookup"><span data-stu-id="64134-131">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="64134-132">Struktura COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="64134-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 [<span data-ttu-id="64134-133">Rozhraní ICorProfilerAssemblyReferenceProvider</span><span class="sxs-lookup"><span data-stu-id="64134-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)