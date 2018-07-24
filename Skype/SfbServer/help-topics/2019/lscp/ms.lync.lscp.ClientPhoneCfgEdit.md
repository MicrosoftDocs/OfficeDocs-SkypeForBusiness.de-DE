---
title: Gerätekonfiguration Erstellen einer neuen oder Bearbeiten einer vorhandenen
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Klicken Sie auf der Seite neue Gerätekonfiguration oder Gerätekonfiguration bearbeiten können Sie erstellen oder Ändern einer Auflistung von Einstellungen zum Verwalten von Skype für Business Phone Edition verwendet. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und die Festlegung, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
ms.openlocfilehash: 9e91313db84a870ef4f85105ddf2b2138d8948aa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997930"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="b5df4-104">Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="b5df4-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="b5df4-105">Klicken Sie auf der Seite **Neue Gerätekonfiguration** oder **Gerätekonfiguration bearbeiten** können Sie erstellen oder Ändern einer Auflistung von Einstellungen zum Verwalten von Skype für Business Phone Edition verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5df4-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="b5df4-106">Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und die Festlegung, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b5df4-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="b5df4-107">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="b5df4-107">Tasks you can perform</span></span>

<span data-ttu-id="b5df4-108">Auf der Seite **Neue Gerätekonfiguration** bzw. **Gerätekonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="b5df4-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="b5df4-109">Hinzufügen einer neuen Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="b5df4-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="b5df4-110">Ändern der Eigenschaften einer vorhandenen Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="b5df4-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="b5df4-111">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="b5df4-111">UI Reference</span></span>

<span data-ttu-id="b5df4-112">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5df4-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="b5df4-113">**Bereich** Gibt den Bereich (Global oder Standort) der Gerätekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="b5df4-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="b5df4-114">**Name** Sie können hinzufügen oder ändern Sie den Namen der Gerätekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="b5df4-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="b5df4-115">**SIP-Sicherheit** Sie können übertragungs- und authentifizierungsanforderungen für Skype für Business Phone Edition-Geräte konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b5df4-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="b5df4-116">Folgende Optionen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b5df4-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="b5df4-117">**Niedrig** Jede Art von Autorisierung- oder Transporttypen zulassen.</span><span class="sxs-lookup"><span data-stu-id="b5df4-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="b5df4-118">**Mittel** NTLM oder Kerberos ist erforderlich für die Benutzerauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b5df4-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="b5df4-119">**Hohe** Erforderlich für die Benutzerauthentifizierung ist NTLM oder Kerberos und TLS für SIP-Verbindungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b5df4-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="b5df4-120">**Protokollierungsstufe** Sie können die Protokollierung für die UC-Gerät aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b5df4-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="b5df4-121">Gültige Werte sind: „Aus“, „Niedrig“, „Mittel“ und „Hoch“.</span><span class="sxs-lookup"><span data-stu-id="b5df4-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="b5df4-122">Der Standardwert lautet „Aus“.</span><span class="sxs-lookup"><span data-stu-id="b5df4-122">The default value is Off.</span></span>
    
- <span data-ttu-id="b5df4-123">**VoIP-Dienstqualität (QoS)** Sie können VoIP-Datenverkehr von einem Skype für Business Phone Edition-Gerät ausgehen zugewiesenen DSCP-Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="b5df4-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="b5df4-124">Der Standardwert lautet 40.</span><span class="sxs-lookup"><span data-stu-id="b5df4-124">The default is 40.</span></span> <span data-ttu-id="b5df4-125">40 ist jedoch nicht den Wert in der Regel für audio-Datenverkehr verwendet. Stattdessen wird audio-Datenverkehr durch den Code DSCP 46 fast immer markiert.</span><span class="sxs-lookup"><span data-stu-id="b5df4-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="b5df4-126">Um die Konsistenz in Ihrem Netzwerk zu verwalten, können Sie diesen Wert auf 46 ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="b5df4-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="b5df4-127">**Telefonsperre** Sie können angeben, ob UC-Telefone selbst automatisch nach einem angegebenen Zeitraum der Inaktivität gesperrt.</span><span class="sxs-lookup"><span data-stu-id="b5df4-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="b5df4-128">Sie können die folgenden Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="b5df4-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="b5df4-129">**Gerätesperre erzwingen** Sie können durch Aktivierung dieses Kontrollkästchens Gerätesperre erzwingen.</span><span class="sxs-lookup"><span data-stu-id="b5df4-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="b5df4-130">**PIN-Mindestlänge** Sie können die Mindestlänge für die persönliche Identifikationsnummer (PIN) angeben, die zum Entsperren des Telefons verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b5df4-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="b5df4-131">Der zulässige Bereich für die PIN-Länge lautet vier bis 15 Stellen.</span><span class="sxs-lookup"><span data-stu-id="b5df4-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="b5df4-132">Die Standardlänge beträgt sechs Stellen.</span><span class="sxs-lookup"><span data-stu-id="b5df4-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="b5df4-133">**Unter Timeout für Telefonsperre** Sie können die minimale Länge der Zeit, bevor die Telefon Sperren selbst angeben.</span><span class="sxs-lookup"><span data-stu-id="b5df4-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="b5df4-134">Der Bereich für das Timeout lautet 0 bis 60 Minuten und der Standardwert beträgt 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="b5df4-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="b5df4-135">Geben Sie den Wert im Format HH:MM:SS ein.</span><span class="sxs-lookup"><span data-stu-id="b5df4-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b5df4-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5df4-136">See also</span></span>

[<span data-ttu-id="b5df4-137">Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="b5df4-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="b5df4-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="b5df4-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)