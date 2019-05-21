---
title: Schema Änderungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Bevor Sie Skype for Business Server bereitstellen und betreiben, müssen Sie die Active Directory-Domänendienste vorbereiten, indem Sie das Schema erweitern. Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die von Skype for Business Server benötigt werden.
ms.openlocfilehash: 34f97f7a37adc23635f938fb12c9a72e22429538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296658"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="7c8b0-104">Schema Änderungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7c8b0-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="7c8b0-105">Bevor Sie Skype for Business Server bereitstellen und betreiben, müssen Sie die Active Directory-Domänendienste vorbereiten, indem Sie das Schema erweitern.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="7c8b0-106">Die Schemaerweiterungen fügen die Klassen und Attribute hinzu, die von Skype for Business Server benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="7c8b0-107">Wenn Sie ein Upgrade von lync Server 2013 auf Skype for Business Server 2015 durchgeführt haben, werden keine Schemaänderungen vorgenommen, und daher gilt dieser Artikel nicht.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="7c8b0-108">Für Skype for Business Server sind mehrere neue Klassen und Attribute erforderlich, und einige vorhandene Klassen und Attribute werden geändert.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="7c8b0-109">Darüber hinaus werden viele Konfigurationsinformationen für Skype for Business Server im zentralen Verwaltungsspeicher statt in AD DS gespeichert, wie in früheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="7c8b0-110">Die folgenden Informationen werden weiterhin in AD DS in Skype for Business Server gespeichert:</span><span class="sxs-lookup"><span data-stu-id="7c8b0-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="7c8b0-111">**Schema Erweiterungen**:</span><span class="sxs-lookup"><span data-stu-id="7c8b0-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="7c8b0-112">Benutzerobjekterweiterungen</span><span class="sxs-lookup"><span data-stu-id="7c8b0-112">User object extensions</span></span>
    
  - <span data-ttu-id="7c8b0-113">Erweiterungen für Klassen zum aufrecht erhalten der Abwärtskompatibilität mit unterstützten vorherigen Versionen von lync Server.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="7c8b0-114">**Daten** (im erweiterten Schema von Skype for Business Server und in vorhandenen Schemaklassen gespeichert):</span><span class="sxs-lookup"><span data-stu-id="7c8b0-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="7c8b0-115">Benutzer SIP Uniform Resource Identifier (URI) und andere Benutzereinstellungen</span><span class="sxs-lookup"><span data-stu-id="7c8b0-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="7c8b0-116">Kontaktobjekte für Anwendungen wie Reaktionsgruppe und Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="7c8b0-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="7c8b0-117">Ein Zeiger auf den zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="7c8b0-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="7c8b0-118">Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt)</span><span class="sxs-lookup"><span data-stu-id="7c8b0-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="7c8b0-119">In diesem Thema werden die Active Directory-Schemaänderungen beschrieben, die von Skype for Business Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="7c8b0-120">Es werden keine Schemaänderungen beschrieben, die in früheren Versionen von Office Communications Server eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="7c8b0-121">Eine Liste der Klassen und deren Beschreibungen finden Sie unter [Schema Klassen und Beschreibungen in Skype for Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="7c8b0-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="7c8b0-122">Eine Liste der Attribute und deren Beschreibungen finden Sie unter [Schema Attribute und Beschreibungen in Skype for Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="7c8b0-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="7c8b0-123">Eine Liste der Klassen mit den Attributen, die Sie enthalten können, finden Sie unter [Schema Attribute nach Klasse in Skype for Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="7c8b0-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="7c8b0-124">Das Attribut msRTCSIP-Präfix identifiziert Klassen und Attribute, die für Skype for Business Server spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="7c8b0-125">Neue Active Directory-Attribute</span><span class="sxs-lookup"><span data-stu-id="7c8b0-125">New Active Directory Attributes</span></span>

<span data-ttu-id="7c8b0-126">In der folgenden Tabelle werden die Active Directory-Attribute beschrieben, die von Skype for Business Server hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="7c8b0-127">**Von Skype for Business Server hinzugefügte Attribute**</span><span class="sxs-lookup"><span data-stu-id="7c8b0-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="7c8b0-128">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="7c8b0-128">**Attribute**</span></span>|<span data-ttu-id="7c8b0-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="7c8b0-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7c8b0-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="7c8b0-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="7c8b0-131">Dieses mehrwertige Attribut enthält Bezeichner für für den Benutzer geltende Aufbewahrungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="7c8b0-132">Aufbewahrungsrichtlinien behalten Postfachelemente für den Benutzer für die Dauer des haltebereichs bei.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="7c8b0-133">Dieses Attribut wird für Exchange 2013 freigegeben.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="7c8b0-134">Attribut msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="7c8b0-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="7c8b0-135">Hierbei handelt es sich um die SIP-Routinggruppen-ID.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="7c8b0-136">Benutzer in der gleichen Gruppe werden für denselben Front-End-Server registriert.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="7c8b0-137">Attribut msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="7c8b0-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="7c8b0-138">Dieses Attribut wird zum Speichern des vom Front-End-Pool verwendeten gespiegelten SQL Server-Back-Ends verwendet.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="7c8b0-139">Geänderte Active Directory-Klassen</span><span class="sxs-lookup"><span data-stu-id="7c8b0-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="7c8b0-140">In der folgenden Tabelle werden die Active Directory-Klassen beschrieben, die von Skype for Business Server geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7c8b0-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="7c8b0-141">**Von Skype for Business Server geänderte Klassen**</span><span class="sxs-lookup"><span data-stu-id="7c8b0-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="7c8b0-142">**Klasse**</span><span class="sxs-lookup"><span data-stu-id="7c8b0-142">**Class**</span></span>|<span data-ttu-id="7c8b0-143">**Änderung**</span><span class="sxs-lookup"><span data-stu-id="7c8b0-143">**Change**</span></span>|<span data-ttu-id="7c8b0-144">**Klasse oder Attribut**</span><span class="sxs-lookup"><span data-stu-id="7c8b0-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7c8b0-145">User</span><span class="sxs-lookup"><span data-stu-id="7c8b0-145">User</span></span>  <br/> |<span data-ttu-id="7c8b0-146">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="7c8b0-146">add: mayContain</span></span>  <br/> <span data-ttu-id="7c8b0-147">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="7c8b0-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="7c8b0-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7c8b0-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="7c8b0-149">Attribut msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="7c8b0-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="7c8b0-150">Kontakt</span><span class="sxs-lookup"><span data-stu-id="7c8b0-150">Contact</span></span>  <br/> |<span data-ttu-id="7c8b0-151">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="7c8b0-151">add: mayContain</span></span>  <br/> <span data-ttu-id="7c8b0-152">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="7c8b0-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="7c8b0-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7c8b0-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="7c8b0-154">Attribut msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="7c8b0-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="7c8b0-155">E-Mail-Empfänger</span><span class="sxs-lookup"><span data-stu-id="7c8b0-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="7c8b0-156">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="7c8b0-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="7c8b0-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="7c8b0-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="7c8b0-158">Attribut msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="7c8b0-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="7c8b0-159">Add: mayContain</span><span class="sxs-lookup"><span data-stu-id="7c8b0-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="7c8b0-160">Attribut msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="7c8b0-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

