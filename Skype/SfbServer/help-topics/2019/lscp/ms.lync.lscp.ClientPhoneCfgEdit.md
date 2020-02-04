---
title: Gerätekonfiguration neues erstellen oder vorhandenes bearbeiten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: Auf der Seite neue Gerätekonfiguration oder Gerätekonfiguration bearbeiten können Sie eine Sammlung von Einstellungen erstellen oder ändern, die für die Verwaltung von Skype for Business Phone Edition verwendet werden. Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und die Festlegung, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.
ms.openlocfilehash: fce3ad1410dc16cc6a238823f11cdba0f4c4c391
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691480"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="1b086-104">Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="1b086-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="1b086-105">Auf der Seite **neue Gerätekonfiguration** oder **Gerätekonfiguration bearbeiten** können Sie eine Sammlung von Einstellungen erstellen oder ändern, die für die Verwaltung von Skype for Business Phone Edition verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b086-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="1b086-106">Diese Einstellungen ermöglichen beispielsweise das Konfigurieren des erforderlichen Sicherheitsmodus, des Protokolliergrads für Geräte, der Einstellungen für die VoIP-Dienstqualität (QoS) und die Festlegung, ob Telefone nach einem bestimmten inaktiven Zeitraum automatisch gesperrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1b086-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="1b086-107">Mögliche Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1b086-107">Tasks you can perform</span></span>

<span data-ttu-id="1b086-108">Auf der Seite **Neue Gerätekonfiguration** bzw. **Gerätekonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="1b086-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="1b086-109">Hinzufügen einer neuen Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="1b086-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="1b086-110">Ändern der Eigenschaften einer vorhandenen Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="1b086-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="1b086-111">Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="1b086-111">UI Reference</span></span>

<span data-ttu-id="1b086-112">In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1b086-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="1b086-113">**Bereich** Identifiziert den Bereich (Global oder Website) der Gerätekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="1b086-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="1b086-114">**Name** Sie können den Namen der Gerätekonfiguration hinzufügen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="1b086-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="1b086-115">**SIP-Sicherheit** Sie können Transport-und Authentifizierungsanforderungen für Skype for Business Phone Edition-Geräte konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1b086-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="1b086-116">Folgende Optionen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="1b086-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="1b086-117">**Niedrige** Erlauben Sie jede Art von Autorisierung oder Transport.</span><span class="sxs-lookup"><span data-stu-id="1b086-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="1b086-118">**Medium** NTLM oder Kerberos ist für die Benutzerauthentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b086-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="1b086-119">**Höchst** NTLM oder Kerberos ist für die Benutzerauthentifizierung erforderlich, und für SIP-Verbindungen ist TLS erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b086-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="1b086-120">**Protokollierungsstufe** Sie können die Protokollierung auf dem UC-Gerät aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1b086-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="1b086-121">Gültige Werte sind: „Aus“, „Niedrig“, „Mittel“ und „Hoch“.</span><span class="sxs-lookup"><span data-stu-id="1b086-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="1b086-122">Der Standardwert lautet „Aus“.</span><span class="sxs-lookup"><span data-stu-id="1b086-122">The default value is Off.</span></span>
    
- <span data-ttu-id="1b086-123">**Sprach Quality of Service (QoS)** Sie können den DSCP-Wert angeben, der dem VoIP-Datenverkehr von einem Skype for Business Phone Edition-Gerät zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1b086-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="1b086-124">Der Standardwert ist 40.</span><span class="sxs-lookup"><span data-stu-id="1b086-124">The default is 40.</span></span> <span data-ttu-id="1b086-125">40 ist jedoch nicht der in der Regel für den Audioverkehr verwendete Wert; Stattdessen wird der Audioverkehr fast immer mit dem DSCP-Code 46 markiert.</span><span class="sxs-lookup"><span data-stu-id="1b086-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="1b086-126">Um die Konsistenz im gesamten Netzwerk zu gewährleisten, sollten Sie diesen Wert in 46 ändern.</span><span class="sxs-lookup"><span data-stu-id="1b086-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="1b086-127">**Telefonsperre** Sie können angeben, ob UC-Telefone nach einem bestimmten Zeitraum der Inaktivität automatisch gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="1b086-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="1b086-128">Sie können die folgenden Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="1b086-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="1b086-129">**Erzwingen der Gerätesperrung** Sie können das Sperren des Geräts erzwingen, indem Sie dieses Kontrollkästchen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1b086-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="1b086-130">**Minimale PIN-Länge** Sie können die Mindestlänge für die persönliche Identifikationsnummer (PIN) angeben, die zum Entsperren des Telefons verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1b086-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="1b086-131">Der zulässige Bereich für die PIN-Länge lautet vier bis 15 Stellen.</span><span class="sxs-lookup"><span data-stu-id="1b086-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="1b086-132">Die Standardlänge beträgt sechs Stellen.</span><span class="sxs-lookup"><span data-stu-id="1b086-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="1b086-133">**Timeout für Telefonsperre** Sie können die minimale Zeitdauer angeben, bevor sich das Telefon selbst sperrt.</span><span class="sxs-lookup"><span data-stu-id="1b086-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="1b086-134">Der Bereich für das Timeout lautet 0 bis 60 Minuten und der Standardwert beträgt 10 Minuten.</span><span class="sxs-lookup"><span data-stu-id="1b086-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="1b086-135">Geben Sie den Wert im Format HH:MM:SS ein.</span><span class="sxs-lookup"><span data-stu-id="1b086-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1b086-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b086-136">See also</span></span>

[<span data-ttu-id="1b086-137">Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="1b086-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="1b086-138">Satz-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="1b086-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
