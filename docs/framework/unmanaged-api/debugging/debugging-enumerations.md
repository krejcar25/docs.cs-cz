---
title: "Ladění výčtů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c24882f2bd9819043bbc786bd2e5f35129a92744
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-enumerations"></a><span data-ttu-id="55ad6-102">Ladění výčtů</span><span class="sxs-lookup"><span data-stu-id="55ad6-102">Debugging Enumerations</span></span>
<span data-ttu-id="55ad6-103">Tato část popisuje nespravovaná vyčíslení, která používá rozhraní API pro ladění.</span><span class="sxs-lookup"><span data-stu-id="55ad6-103">This section describes the unmanaged enumerations that the debugging API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55ad6-104">V tomto oddílu</span><span class="sxs-lookup"><span data-stu-id="55ad6-104">In This Section</span></span>  
 [<span data-ttu-id="55ad6-105">CLR_DEBUGGING_PROCESS_FLAGS – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-105">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 <span data-ttu-id="55ad6-106">Obsahuje hodnoty, které jsou používány [iclrdebugging::openvirtualprocess –](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="55ad6-106">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="55ad6-107">CLRDataEnumMemoryFlags – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-107">CLRDataEnumMemoryFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 <span data-ttu-id="55ad6-108">Určuje, které oblasti paměti volání [iclrdataenummemoryregions::enummemoryregions –](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) metoda by měla obsahovat.</span><span class="sxs-lookup"><span data-stu-id="55ad6-108">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
 [<span data-ttu-id="55ad6-109">COR_PUB_ENUMPROCESS – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-109">COR_PUB_ENUMPROCESS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 <span data-ttu-id="55ad6-110">Určuje typ procesu výčet.</span><span class="sxs-lookup"><span data-stu-id="55ad6-110">Identifies the type of process to be enumerated.</span></span>  
  
 [<span data-ttu-id="55ad6-111">CorDebugBlockingReason – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-111">CorDebugBlockingReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 <span data-ttu-id="55ad6-112">Určuje z důvodů, proč může zablokování vlákna na daný objekt.</span><span class="sxs-lookup"><span data-stu-id="55ad6-112">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
 <span data-ttu-id="55ad6-113">CorDebugChainReason</span><span class="sxs-lookup"><span data-stu-id="55ad6-113">CorDebugChainReason</span></span>  
 <span data-ttu-id="55ad6-114">Označuje důvod nebo důvody pro zahájení řetěz volání.</span><span class="sxs-lookup"><span data-stu-id="55ad6-114">Indicates the reason or reasons for the initiation of a call chain.</span></span>  
  
 [<span data-ttu-id="55ad6-115">Výčet Cordebugcodeinvokekind</span><span class="sxs-lookup"><span data-stu-id="55ad6-115">CorDebugCodeInvokeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 <span data-ttu-id="55ad6-116">Popisuje, jak exportované funkce vyvolá spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="55ad6-116">Describes how an exported function invokes managed code.</span></span>  
  
 [<span data-ttu-id="55ad6-117">Výčet Cordebugcodeinvokepurpose</span><span class="sxs-lookup"><span data-stu-id="55ad6-117">CorDebugCodeInvokePurpose Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 <span data-ttu-id="55ad6-118">Popisuje, proč exportované funkce volá spravovaného kódu.</span><span class="sxs-lookup"><span data-stu-id="55ad6-118">Describes why an exported function calls managed code.</span></span>  
  
 <span data-ttu-id="55ad6-119">CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="55ad6-119">CorDebugCreateProcessFlags</span></span>  
 <span data-ttu-id="55ad6-120">Poskytuje další možnosti ladění, které mohou být používány volání [icordebug::CreateProcess –](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="55ad6-120">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
 [<span data-ttu-id="55ad6-121">Výčet Cordebugdebugeventkind</span><span class="sxs-lookup"><span data-stu-id="55ad6-121">CorDebugDebugEventKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 <span data-ttu-id="55ad6-122">Určuje typ události, jejichž informace dekóduje ji [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="55ad6-122">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
 [<span data-ttu-id="55ad6-123">Výčet Cordebugdecodeeventflagswindows</span><span class="sxs-lookup"><span data-stu-id="55ad6-123">CorDebugDecodeEventFlagsWindows Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 <span data-ttu-id="55ad6-124">Poskytuje další informace o ladění událostí na platformě Windows.</span><span class="sxs-lookup"><span data-stu-id="55ad6-124">Provides additional information about debug events on the Windows platform.</span></span>  
  
 <span data-ttu-id="55ad6-125">CorDebugExceptionCallbackType</span><span class="sxs-lookup"><span data-stu-id="55ad6-125">CorDebugExceptionCallbackType</span></span>  
 <span data-ttu-id="55ad6-126">Určuje typ zpětné volání, které se provádí z [icordebugmanagedcallback2::Exception –](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) událostí.</span><span class="sxs-lookup"><span data-stu-id="55ad6-126">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
 [<span data-ttu-id="55ad6-127">CorDebugExceptionFlags – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-127">CorDebugExceptionFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 <span data-ttu-id="55ad6-128">Poskytuje další informace o výjimce.</span><span class="sxs-lookup"><span data-stu-id="55ad6-128">Provides additional information about an exception.</span></span>  
  
 <span data-ttu-id="55ad6-129">CorDebugExceptionUnwindCallbackType</span><span class="sxs-lookup"><span data-stu-id="55ad6-129">CorDebugExceptionUnwindCallbackType</span></span>  
 <span data-ttu-id="55ad6-130">Označuje událost, která se během fáze unwind signalizace podle zpětné volání.</span><span class="sxs-lookup"><span data-stu-id="55ad6-130">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 [<span data-ttu-id="55ad6-131">CorDebugGCType – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-131">CorDebugGCType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 <span data-ttu-id="55ad6-132">Určuje, zda má systém uvolňování běží na pracovní stanici nebo na serveru.</span><span class="sxs-lookup"><span data-stu-id="55ad6-132">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
 [<span data-ttu-id="55ad6-133">CorDebugGenerationTypes – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-133">CorDebugGenerationTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 <span data-ttu-id="55ad6-134">Spravovaná halda určuje generování oblasti paměti.</span><span class="sxs-lookup"><span data-stu-id="55ad6-134">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
 <span data-ttu-id="55ad6-135">CorDebugHandleType</span><span class="sxs-lookup"><span data-stu-id="55ad6-135">CorDebugHandleType</span></span>  
 <span data-ttu-id="55ad6-136">Určuje typ popisovače.</span><span class="sxs-lookup"><span data-stu-id="55ad6-136">Indicates the handle type.</span></span>  
  
 [<span data-ttu-id="55ad6-137">CorDebugIlToNativeMappingTypes – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-137">CorDebugIlToNativeMappingTypes Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 <span data-ttu-id="55ad6-138">Určuje, jestli konkrétní rozsah nativní pokyny odpovídá speciální kód oblasti.</span><span class="sxs-lookup"><span data-stu-id="55ad6-138">Indicates whether a particular range of native instructions corresponds to a special code region.</span></span>  
  
 <span data-ttu-id="55ad6-139">CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="55ad6-139">CorDebugIntercept</span></span>  
 <span data-ttu-id="55ad6-140">Určuje typy kód, který může mít stupně do.</span><span class="sxs-lookup"><span data-stu-id="55ad6-140">Indicates the types of code that can be stepped into.</span></span>  
  
 [<span data-ttu-id="55ad6-141">CorDebugInterfaceVersion – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-141">CorDebugInterfaceVersion Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 <span data-ttu-id="55ad6-142">Určuje verzi rozhraní .NET Framework nebo verzi rozhraní .NET Framework, ve kterém byla zavedena rozhraní.</span><span class="sxs-lookup"><span data-stu-id="55ad6-142">Specifies either a version of the .NET Framework, or the version of the .NET Framework in which an interface was introduced.</span></span>  
  
 <span data-ttu-id="55ad6-143">CorDebugInternalFrameType</span><span class="sxs-lookup"><span data-stu-id="55ad6-143">CorDebugInternalFrameType</span></span>  
 <span data-ttu-id="55ad6-144">Určuje typ rámce zásobníku.</span><span class="sxs-lookup"><span data-stu-id="55ad6-144">Identifies the type of stack frame.</span></span>  
  
 [<span data-ttu-id="55ad6-145">CorDebugJITCompilerFlags – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-145">CorDebugJITCompilerFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 <span data-ttu-id="55ad6-146">Obsahuje hodnoty, které ovlivňují chování objektu spravovaného kompilátoru za běhu (JIT).</span><span class="sxs-lookup"><span data-stu-id="55ad6-146">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
 [<span data-ttu-id="55ad6-147">CorDebugJITCompilerFlagsDeprecated – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-147">CorDebugJITCompilerFlagsDeprecated Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 <span data-ttu-id="55ad6-148">Zastaralé.</span><span class="sxs-lookup"><span data-stu-id="55ad6-148">Obsolete.</span></span> <span data-ttu-id="55ad6-149">Použití `CORDEBUG_JIT_DEFAULT` členem [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) – výčet místo.</span><span class="sxs-lookup"><span data-stu-id="55ad6-149">Use the `CORDEBUG_JIT_DEFAULT` member of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration instead.</span></span>  
  
 <span data-ttu-id="55ad6-150">CorDebugMappingResult</span><span class="sxs-lookup"><span data-stu-id="55ad6-150">CorDebugMappingResult</span></span>  
 <span data-ttu-id="55ad6-151">Poskytuje podrobnosti o tom, jak byla získána hodnota ukazatele instrukce (IP).</span><span class="sxs-lookup"><span data-stu-id="55ad6-151">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
 [<span data-ttu-id="55ad6-152">CorDebugMDAFlags – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-152">CorDebugMDAFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 <span data-ttu-id="55ad6-153">Určuje stav vláken, na kterém je aktivována, Pomocník spravovaného ladění (MDA).</span><span class="sxs-lookup"><span data-stu-id="55ad6-153">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
 [<span data-ttu-id="55ad6-154">CorDebugNGenPolicy – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-154">CorDebugNGenPolicy Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 <span data-ttu-id="55ad6-155">Obsahuje hodnotu, která určuje, zda ladicí program načte nativní bitové kopie (NGen) z mezipaměť nativních bitových kopií.</span><span class="sxs-lookup"><span data-stu-id="55ad6-155">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
 [<span data-ttu-id="55ad6-156">Výčet Cordebugplatform</span><span class="sxs-lookup"><span data-stu-id="55ad6-156">CorDebugPlatform Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 <span data-ttu-id="55ad6-157">Poskytuje cílové platformy hodnoty, které jsou používány [icordebugdatatarget::getplatform –](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) metoda.</span><span class="sxs-lookup"><span data-stu-id="55ad6-157">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
 [<span data-ttu-id="55ad6-158">Výčet Cordebugrecordformat</span><span class="sxs-lookup"><span data-stu-id="55ad6-158">CorDebugRecordFormat Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 <span data-ttu-id="55ad6-159">Popisuje formát dat v bajtové pole obsahující informace o události ladění nativního výjimka.</span><span class="sxs-lookup"><span data-stu-id="55ad6-159">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
 <span data-ttu-id="55ad6-160">CorDebugRegister</span><span class="sxs-lookup"><span data-stu-id="55ad6-160">CorDebugRegister</span></span>  
 <span data-ttu-id="55ad6-161">Určuje registry spojené s danou procesoru architektura.</span><span class="sxs-lookup"><span data-stu-id="55ad6-161">Specifies the registers associated with a given processor architecture.</span></span>  
  
 [<span data-ttu-id="55ad6-162">CorDebugSetContextFlag – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-162">CorDebugSetContextFlag Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 <span data-ttu-id="55ad6-163">Určuje, zda kontext je z aktivní (nebo listu) s rámečkem v zásobníku nebo je poškozený podle unwinding z jiné rámce.</span><span class="sxs-lookup"><span data-stu-id="55ad6-163">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
 [<span data-ttu-id="55ad6-164">Výčet Cordebugstatechange</span><span class="sxs-lookup"><span data-stu-id="55ad6-164">CorDebugStateChange Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 <span data-ttu-id="55ad6-165">Popisuje množství uložené v mezipaměti dat, která musí být odstraněn podle změn do procesu.</span><span class="sxs-lookup"><span data-stu-id="55ad6-165">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
 <span data-ttu-id="55ad6-166">CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="55ad6-166">CorDebugStepReason</span></span>  
 <span data-ttu-id="55ad6-167">Určuje výsledek jednotlivé kroky.</span><span class="sxs-lookup"><span data-stu-id="55ad6-167">Indicates the outcome of an individual step.</span></span>  
  
 <span data-ttu-id="55ad6-168">CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="55ad6-168">CorDebugThreadState</span></span>  
 <span data-ttu-id="55ad6-169">Určuje stav vláken pro ladění.</span><span class="sxs-lookup"><span data-stu-id="55ad6-169">Specifies the state of a thread for debugging.</span></span>  
  
 <span data-ttu-id="55ad6-170">\>CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="55ad6-170">\>CorDebugUnmappedStop</span></span>  
 <span data-ttu-id="55ad6-171">Určuje typ nenamapovaný kód, který můžete aktivovat zastavení provádění kódu pomocí krokovače.</span><span class="sxs-lookup"><span data-stu-id="55ad6-171">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
 <span data-ttu-id="55ad6-172">CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="55ad6-172">CorDebugUserState</span></span>  
 <span data-ttu-id="55ad6-173">Určuje stav uživatele vlákna.</span><span class="sxs-lookup"><span data-stu-id="55ad6-173">Indicates the user state of a thread.</span></span>  
  
 [<span data-ttu-id="55ad6-174">CorGCReferenceType – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-174">CorGCReferenceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 <span data-ttu-id="55ad6-175">Určuje zdroj objekt tak, aby se uvolňování paměti.</span><span class="sxs-lookup"><span data-stu-id="55ad6-175">Identifies the source of an object to be garbage-collected.</span></span>  
  
 [<span data-ttu-id="55ad6-176">Výčet Ilcodekind</span><span class="sxs-lookup"><span data-stu-id="55ad6-176">ILCodeKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 <span data-ttu-id="55ad6-177">Obsahuje hodnoty, které určují, jestli je přístup k místní proměnné nebo kódu přidaném v ReJIT instrumentace profileru ladicího programu.</span><span class="sxs-lookup"><span data-stu-id="55ad6-177">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="55ad6-178">LoggingLevelEnum – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-178">LoggingLevelEnum Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 <span data-ttu-id="55ad6-179">Určuje úroveň závažnosti popisný zprávu, která se zapíšou do protokolu událostí, když spravované vlákno protokoluje nějakou událost.</span><span class="sxs-lookup"><span data-stu-id="55ad6-179">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
 [<span data-ttu-id="55ad6-180">LogSwitchCallReason – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-180">LogSwitchCallReason Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 <span data-ttu-id="55ad6-181">Určuje operaci, která byla provedena na přepínači ladění nebo trasování.</span><span class="sxs-lookup"><span data-stu-id="55ad6-181">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
 [<span data-ttu-id="55ad6-182">VariableLocationType – výčet</span><span class="sxs-lookup"><span data-stu-id="55ad6-182">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 <span data-ttu-id="55ad6-183">Označuje typ nativní umístění proměnné.</span><span class="sxs-lookup"><span data-stu-id="55ad6-183">Indicates the native location type of a variable.</span></span>  
  
 [<span data-ttu-id="55ad6-184">Výčet Writeablemetadataupdatemode</span><span class="sxs-lookup"><span data-stu-id="55ad6-184">WriteableMetadataUpdateMode Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 <span data-ttu-id="55ad6-185">Obsahuje hodnoty, které určují, zda jsou viditelné pro ladicí program aktualizace v paměti pro metadata.</span><span class="sxs-lookup"><span data-stu-id="55ad6-185">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="55ad6-186">Související oddíly</span><span class="sxs-lookup"><span data-stu-id="55ad6-186">Related Sections</span></span>  
 [<span data-ttu-id="55ad6-187">Ladění tříd typu coclass</span><span class="sxs-lookup"><span data-stu-id="55ad6-187">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="55ad6-188">Ladění v rozhraní</span><span class="sxs-lookup"><span data-stu-id="55ad6-188">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [<span data-ttu-id="55ad6-189">Globální statické funkce ladění</span><span class="sxs-lookup"><span data-stu-id="55ad6-189">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="55ad6-190">Struktury pro ladění</span><span class="sxs-lookup"><span data-stu-id="55ad6-190">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)