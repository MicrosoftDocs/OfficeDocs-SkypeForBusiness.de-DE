---
title: Gerätekonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: Klicken Sie auf der Seite neue Gerätekonfiguration oder Gerätekonfiguration bearbeiten können Sie erstellen oder Ändern einer Auflistung von Einstellungen zum Verwalten von Skype für Business Phone Edition verwendet. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und die Festlegung, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
ms.openlocfilehash: ed1f002cd0d8c0465a765c04c3efb4367c6f99fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234679"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="f8707-104">Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="f8707-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="f8707-105">Klicken Sie auf der Seite **Neue Gerätekonfiguration** oder **Gerätekonfiguration bearbeiten** können Sie erstellen oder Ändern einer Auflistung von Einstellungen zum Verwalten von Skype für Business Phone Edition verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8707-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="f8707-106">Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und die Festlegung, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f8707-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="f8707-107">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="f8707-107">Tasks you can perform</span></span>

<span data-ttu-id="f8707-108">Auf der Seite **Neue Gerätekonfiguration** bzw. **Gerätekonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="f8707-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="f8707-109">Hinzufügen einer neuen Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="f8707-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="f8707-110">Ändern der Eigenschaften einer vorhandenen Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="f8707-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="f8707-111">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="f8707-111">UI Reference</span></span>

<span data-ttu-id="f8707-112">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f8707-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="f8707-113">**Bereich** Gibt den Bereich (Global oder Standort) der Gerätekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8707-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="f8707-114">**Name** Sie können hinzufügen oder ändern Sie den Namen der Gerätekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8707-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="f8707-115">**SIP-Sicherheit** Sie können übertragungs- und authentifizierungsanforderungen für Skype für Business Phone Edition-Geräte konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f8707-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="f8707-116">Folgende Optionen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f8707-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="f8707-117">**Niedrig** Jede Art von Autorisierung- oder Transporttypen zulassen.</span><span class="sxs-lookup"><span data-stu-id="f8707-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="f8707-118">**Mittel** NTLM oder Kerberos ist erforderlich für die Benutzerauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f8707-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="f8707-119">**Hohe** Erforderlich für die Benutzerauthentifizierung ist NTLM oder Kerberos und TLS für SIP-Verbindungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f8707-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="f8707-120">**Protokollierungsstufe** Sie können die Protokollierung für die UC-Gerät aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f8707-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="f8707-121">Gültige Werte sind: „Aus“, „Niedrig“, „Mittel“ und „Hoch“.</span><span class="sxs-lookup"><span data-stu-id="f8707-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="f8707-122">Der Standardwert lautet „Aus“.</span><span class="sxs-lookup"><span data-stu-id="f8707-122">The default value is Off.</span></span>
    
- <span data-ttu-id="f8707-123">**VoIP-Dienstqualität (QoS)** Sie können VoIP-Datenverkehr von einem Skype für Business Phone Edition-Gerät ausgehen zugewiesenen DSCP-Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="f8707-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="f8707-124">Der Standardwert lautet 40.</span><span class="sxs-lookup"><span data-stu-id="f8707-124">The default is 40.</span></span> <span data-ttu-id="f8707-125">40 ist jedoch nicht den Wert in der Regel für audio-Datenverkehr verwendet. Stattdessen wird audio-Datenverkehr durch den Code DSCP 46 fast immer markiert.</span><span class="sxs-lookup"><span data-stu-id="f8707-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="f8707-126">Um die Konsistenz in Ihrem Netzwerk zu verwalten, können Sie diesen Wert auf 46 ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f8707-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="f8707-127">**Telefonsperre** Sie können angeben, ob UC-Telefone selbst automatisch nach einem angegebenen Zeitraum der Inaktivität gesperrt.</span><span class="sxs-lookup"><span data-stu-id="f8707-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="f8707-128">Sie können die folgenden Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f8707-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="f8707-129">**Gerätesperre erzwingen** Sie können durch Aktivierung dieses Kontrollkästchens Gerätesperre erzwingen.</span><span class="sxs-lookup"><span data-stu-id="f8707-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="f8707-130">**PIN-Mindestlänge** Sie können die Mindestlänge für die persönliche Identifikationsnummer (PIN) angeben, die zum Entsperren des Telefons verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f8707-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="f8707-131">Der zulässige Bereich für die PIN-Länge lautet vier bis 15 Stellen.</span><span class="sxs-lookup"><span data-stu-id="f8707-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="f8707-132">Die Standardlänge beträgt sechs Stellen.</span><span class="sxs-lookup"><span data-stu-id="f8707-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="f8707-133">**Unter Timeout für Telefonsperre** Sie können die minimale Länge der Zeit, bevor die Telefon Sperren selbst angeben.</span><span class="sxs-lookup"><span data-stu-id="f8707-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="f8707-134">Der Bereich für das Timeout lautet 0 bis 60 Minuten und der Standardwert beträgt 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="f8707-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="f8707-135">Geben Sie den Wert im Format HH:MM:SS ein.</span><span class="sxs-lookup"><span data-stu-id="f8707-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f8707-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8707-136">See also</span></span>

[<span data-ttu-id="f8707-137">Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="f8707-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="f8707-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8707-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
