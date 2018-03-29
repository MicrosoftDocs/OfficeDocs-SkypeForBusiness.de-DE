---
title: Schemaänderungen in Skype für Business Server
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
ms.openlocfilehash: 42b4417311c557323535aa03053ccb03d95cc840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="845ce-104">Schemaänderungen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="845ce-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="845ce-105">Vor der Bereitstellung und Betrieb von Skype für Business Server müssen Sie Active Directory-Domänendienste durch Erweitern des Schemas vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="845ce-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="845ce-106">Durch die schemaerweiterungen hinzufügen die Klassen und Attribute, die von Skype für Business Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="845ce-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span> 
  
<span data-ttu-id="845ce-107">Skype für Business Server erfordert einige neue Klassen und Attribute und ändert einige vorhandene Klassen und Attribute.</span><span class="sxs-lookup"><span data-stu-id="845ce-107">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="845ce-108">Darüber hinaus wird wie in früheren Versionen viel Konfigurationsinformationen für Skype für Business Server in der zentralen Verwaltungsspeichers statt in AD DS gespeichert.</span><span class="sxs-lookup"><span data-stu-id="845ce-108">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="845ce-109">Die folgende Informationen wird weiterhin in AD DS in Skype für Business Server gespeichert:</span><span class="sxs-lookup"><span data-stu-id="845ce-109">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="845ce-110">**Schemaerweiterungen**:</span><span class="sxs-lookup"><span data-stu-id="845ce-110">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="845ce-111">Benutzerobjekterweiterungen</span><span class="sxs-lookup"><span data-stu-id="845ce-111">User object extensions</span></span>
    
  - <span data-ttu-id="845ce-112">Erweiterungen für Klassen zum Aufrechterhalten der Abwärtskompatibilität mit unterstützten Vorgängerversionen von Lync Server.</span><span class="sxs-lookup"><span data-stu-id="845ce-112">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="845ce-113">**Daten** (gespeichert in Skype für erweiterte Business Server-Schema und in vorhandenen Schemaklassen):</span><span class="sxs-lookup"><span data-stu-id="845ce-113">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="845ce-114">Benutzer SIP-URI Uniform Resource Identifier () und andere Einstellungen</span><span class="sxs-lookup"><span data-stu-id="845ce-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="845ce-115">Kontaktobjekte für Anwendungen wie Reaktionsgruppe und die Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="845ce-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="845ce-116">Ein Zeiger auf den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="845ce-116">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="845ce-117">Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)</span><span class="sxs-lookup"><span data-stu-id="845ce-117">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="845ce-118">In diesem Thema werden die Active Directory-schemaänderungen von Skype für Business Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="845ce-118">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="845ce-119">Es wird nicht schemaänderungen beschrieben, die durch frühere Versionen von Office Communications Server eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="845ce-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="845ce-120">Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schemaklassen und Beschreibungen in Skype für Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="845ce-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="845ce-121">Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schemaattribute und Beschreibungen in Skype für Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="845ce-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="845ce-122">Eine Liste der Klassen mit den Attributen können sie enthalten, finden Sie unter [Schemaattribute nach Klasse in Skype für Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="845ce-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="845ce-123">Das Präfix "MsRTCSIP" identifiziert Klassen und Attribute, die speziell für Skype für Business Server sind.</span><span class="sxs-lookup"><span data-stu-id="845ce-123">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="845ce-124">Neue Active Directory-Attribute</span><span class="sxs-lookup"><span data-stu-id="845ce-124">New Active Directory Attributes</span></span>

<span data-ttu-id="845ce-125">Die folgende Tabelle beschreibt die Active Directory-Attribute, die von Skype für Business Server hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="845ce-125">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="845ce-126">**Skype für Business Server hinzugefügte Attribute**</span><span class="sxs-lookup"><span data-stu-id="845ce-126">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="845ce-127">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="845ce-127">**Attribute**</span></span>|<span data-ttu-id="845ce-128">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="845ce-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="845ce-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="845ce-129">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="845ce-130">Dieses mehrwertige Attribut enthält Bezeichner für Richtlinien enthalten, die für den Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="845ce-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="845ce-131">Halten Sie, dass Richtlinien für die Dauer des Haltestatus Postfachelemente für den Benutzer beibehalten.</span><span class="sxs-lookup"><span data-stu-id="845ce-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="845ce-132">Dieses Attribut ist für Exchange 2013 freigegeben.</span><span class="sxs-lookup"><span data-stu-id="845ce-132">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="845ce-133">MsRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="845ce-133">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="845ce-134">Hierbei handelt es sich um die SIP-routing Gruppen-ID.</span><span class="sxs-lookup"><span data-stu-id="845ce-134">This is the SIP routing group ID.</span></span> <span data-ttu-id="845ce-135">Benutzer in der gleichen Gruppe werden auf dem gleichen Front-End-Server registriert.</span><span class="sxs-lookup"><span data-stu-id="845ce-135">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="845ce-136">MsRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="845ce-136">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="845ce-137">Dieses Attribut wird zum Speichern der gespiegelten SQL Server-Back-End von den Front-End-Pool verwendet.</span><span class="sxs-lookup"><span data-stu-id="845ce-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="845ce-138">Geänderte Active Directory-Klassen</span><span class="sxs-lookup"><span data-stu-id="845ce-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="845ce-139">Die folgende Tabelle beschreibt die Active Directory-Klassen, die von Skype für Business Server geändert werden.</span><span class="sxs-lookup"><span data-stu-id="845ce-139">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="845ce-140">**Von Skype für Business Server geänderte Klassen**</span><span class="sxs-lookup"><span data-stu-id="845ce-140">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="845ce-141">**Klasse**</span><span class="sxs-lookup"><span data-stu-id="845ce-141">**Class**</span></span>|<span data-ttu-id="845ce-142">**Änderung**</span><span class="sxs-lookup"><span data-stu-id="845ce-142">**Change**</span></span>|<span data-ttu-id="845ce-143">**Klasse oder eines Attributs**</span><span class="sxs-lookup"><span data-stu-id="845ce-143">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="845ce-144">Benutzer</span><span class="sxs-lookup"><span data-stu-id="845ce-144">User</span></span>  <br/> |<span data-ttu-id="845ce-145">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="845ce-145">add: mayContain</span></span>  <br/> <span data-ttu-id="845ce-146">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="845ce-146">add: mayContain</span></span>  <br/> |<span data-ttu-id="845ce-147">Proxyadressen</span><span class="sxs-lookup"><span data-stu-id="845ce-147">ProxyAddresses</span></span>  <br/> <span data-ttu-id="845ce-148">MsRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="845ce-148">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="845ce-149">Kontakt</span><span class="sxs-lookup"><span data-stu-id="845ce-149">Contact</span></span>  <br/> |<span data-ttu-id="845ce-150">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="845ce-150">add: mayContain</span></span>  <br/> <span data-ttu-id="845ce-151">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="845ce-151">add: mayContain</span></span>  <br/> |<span data-ttu-id="845ce-152">Proxyadressen</span><span class="sxs-lookup"><span data-stu-id="845ce-152">ProxyAddresses</span></span>  <br/> <span data-ttu-id="845ce-153">MsRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="845ce-153">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="845ce-154">E-Mail-Empfänger</span><span class="sxs-lookup"><span data-stu-id="845ce-154">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="845ce-155">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="845ce-155">add: mayContain</span></span>  <br/> |<span data-ttu-id="845ce-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="845ce-156">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="845ce-157">MsRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="845ce-157">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="845ce-158">hinzufügen: MayContain</span><span class="sxs-lookup"><span data-stu-id="845ce-158">add: mayContain</span></span>  <br/> |<span data-ttu-id="845ce-159">MsRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="845ce-159">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

