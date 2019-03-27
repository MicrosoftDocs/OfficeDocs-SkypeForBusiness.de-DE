---
title: Schemaänderungen in Skype für Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Vor der Bereitstellung und Betrieb von Skype für Business Server müssen Sie Active Directory-Domänendienste durch Erweitern des Schemas vorbereiten. Durch die schemaerweiterungen hinzufügen die Klassen und Attribute, die von Skype für Business Server erforderlich sind.
ms.openlocfilehash: ba76f57197e9cd812163c8abac5f51005933eace
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874640"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="99cd8-104">Schemaänderungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="99cd8-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="99cd8-105">Vor der Bereitstellung und Betrieb von Skype für Business Server müssen Sie Active Directory-Domänendienste durch Erweitern des Schemas vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="99cd8-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="99cd8-106">Durch die schemaerweiterungen hinzufügen die Klassen und Attribute, die von Skype für Business Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="99cd8-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="99cd8-107">Wenn Sie von Lync Server 2013 auf Skype für Business Server 2015 durchführen, werden keine schemaänderungen vorgenommen, und daher in diesem Artikel wird nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="99cd8-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="99cd8-108">Skype für Business Server erfordert einige neue Klassen und Attribute und ändert einige vorhandene Klassen und Attribute.</span><span class="sxs-lookup"><span data-stu-id="99cd8-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="99cd8-109">Darüber hinaus wird wie in früheren Versionen viel Konfigurationsinformationen für Skype für Business Server in der zentralen Verwaltungsspeichers statt in AD DS gespeichert.</span><span class="sxs-lookup"><span data-stu-id="99cd8-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="99cd8-110">Die folgende Informationen wird weiterhin in AD DS in Skype für Business Server gespeichert:</span><span class="sxs-lookup"><span data-stu-id="99cd8-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="99cd8-111">**Schemaerweiterungen**:</span><span class="sxs-lookup"><span data-stu-id="99cd8-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="99cd8-112">Benutzerobjekterweiterungen</span><span class="sxs-lookup"><span data-stu-id="99cd8-112">User object extensions</span></span>
    
  - <span data-ttu-id="99cd8-113">Erweiterungen für Klassen zum Aufrechterhalten der Abwärtskompatibilität mit unterstützten Vorgängerversionen von Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99cd8-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="99cd8-114">**Daten** (gespeichert in Skype für erweiterte Business Server-Schema und in vorhandenen Schemaklassen):</span><span class="sxs-lookup"><span data-stu-id="99cd8-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="99cd8-115">Benutzer SIP-URI Uniform Resource Identifier () und andere Einstellungen</span><span class="sxs-lookup"><span data-stu-id="99cd8-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="99cd8-116">Kontaktobjekte für Anwendungen wie Reaktionsgruppe und die Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="99cd8-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="99cd8-117">Ein Zeiger auf den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="99cd8-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="99cd8-118">Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)</span><span class="sxs-lookup"><span data-stu-id="99cd8-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="99cd8-119">In diesem Thema werden die Active Directory-schemaänderungen von Skype für Business Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="99cd8-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="99cd8-120">Es wird nicht schemaänderungen beschrieben, die durch frühere Versionen von Office Communications Server eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="99cd8-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="99cd8-121">Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schemaklassen und Beschreibungen in Skype für Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="99cd8-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="99cd8-122">Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schemaattribute und Beschreibungen in Skype für Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="99cd8-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="99cd8-123">Eine Liste der Klassen mit den Attributen können sie enthalten, finden Sie unter [Schemaattribute nach Klasse in Skype für Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="99cd8-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="99cd8-124">Das Präfix "MsRTCSIP" identifiziert Klassen und Attribute, die speziell für Skype für Business Server sind.</span><span class="sxs-lookup"><span data-stu-id="99cd8-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="99cd8-125">Neue Active Directory-Attribute</span><span class="sxs-lookup"><span data-stu-id="99cd8-125">New Active Directory Attributes</span></span>

<span data-ttu-id="99cd8-126">Die folgende Tabelle beschreibt die Active Directory-Attribute, die von Skype für Business Server hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="99cd8-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="99cd8-127">**Skype für Business Server hinzugefügte Attribute**</span><span class="sxs-lookup"><span data-stu-id="99cd8-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="99cd8-128">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="99cd8-128">**Attribute**</span></span>|<span data-ttu-id="99cd8-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="99cd8-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="99cd8-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="99cd8-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="99cd8-131">Dieses mehrwertige Attribut enthält Bezeichner für Richtlinien enthalten, die für den Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="99cd8-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="99cd8-132">Halten Sie, dass Richtlinien für die Dauer des Haltestatus Postfachelemente für den Benutzer beibehalten.</span><span class="sxs-lookup"><span data-stu-id="99cd8-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="99cd8-133">Dieses Attribut ist für Exchange 2013 freigegeben.</span><span class="sxs-lookup"><span data-stu-id="99cd8-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="99cd8-134">MsRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="99cd8-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="99cd8-135">Hierbei handelt es sich um die SIP-routing Gruppen-ID.</span><span class="sxs-lookup"><span data-stu-id="99cd8-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="99cd8-136">Benutzer in der gleichen Gruppe werden auf dem gleichen Front-End-Server registriert.</span><span class="sxs-lookup"><span data-stu-id="99cd8-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="99cd8-137">MsRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="99cd8-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="99cd8-138">Dieses Attribut wird zum Speichern der gespiegelten SQL Server-Back-End von den Front-End-Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="99cd8-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="99cd8-139">Geänderte Active Directory-Klassen</span><span class="sxs-lookup"><span data-stu-id="99cd8-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="99cd8-140">Die folgende Tabelle beschreibt die Active Directory-Klassen, die von Skype für Business Server geändert werden.</span><span class="sxs-lookup"><span data-stu-id="99cd8-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="99cd8-141">**Von Skype für Business Server geänderte Klassen**</span><span class="sxs-lookup"><span data-stu-id="99cd8-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="99cd8-142">**Klasse**</span><span class="sxs-lookup"><span data-stu-id="99cd8-142">**Class**</span></span>|<span data-ttu-id="99cd8-143">**Änderung**</span><span class="sxs-lookup"><span data-stu-id="99cd8-143">**Change**</span></span>|<span data-ttu-id="99cd8-144">**Klasse oder eines Attributs**</span><span class="sxs-lookup"><span data-stu-id="99cd8-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="99cd8-145">User</span><span class="sxs-lookup"><span data-stu-id="99cd8-145">User</span></span>  <br/> |<span data-ttu-id="99cd8-146">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="99cd8-146">add: mayContain</span></span>  <br/> <span data-ttu-id="99cd8-147">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="99cd8-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="99cd8-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="99cd8-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="99cd8-149">MsRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="99cd8-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="99cd8-150">Kontakt</span><span class="sxs-lookup"><span data-stu-id="99cd8-150">Contact</span></span>  <br/> |<span data-ttu-id="99cd8-151">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="99cd8-151">add: mayContain</span></span>  <br/> <span data-ttu-id="99cd8-152">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="99cd8-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="99cd8-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="99cd8-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="99cd8-154">MsRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="99cd8-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="99cd8-155">E-Mail-Empfänger</span><span class="sxs-lookup"><span data-stu-id="99cd8-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="99cd8-156">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="99cd8-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="99cd8-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="99cd8-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="99cd8-158">MsRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="99cd8-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="99cd8-159">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="99cd8-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="99cd8-160">MsRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="99cd8-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

