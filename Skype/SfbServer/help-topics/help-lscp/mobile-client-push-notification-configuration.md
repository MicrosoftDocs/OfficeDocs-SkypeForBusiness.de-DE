---
title: Mobiler Client Pushbenachrichtigungskonfiguration
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Um die Microsoft-Pushbenachrichtigungen und Apple-Pushbenachrichtigungen zu konfigurieren, müssen Sie eine Richtlinie definieren, welche Arten von Pushbenachrichtigungen Sie benötigen, um erstellen.
ms.openlocfilehash: 946e083ab9f3f4dbc2b59f7f3026ec3a6dd5ed19
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="35abd-103">Mobiler Client: Konfiguration für Pushbenachrichtigung</span><span class="sxs-lookup"><span data-stu-id="35abd-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="35abd-104">Um die **Microsoft-Pushbenachrichtigungen** und **Apple-Pushbenachrichtigungen**zu konfigurieren, müssen Sie eine Richtlinie definieren, welche Arten von Pushbenachrichtigungen benötigten erstellen.</span><span class="sxs-lookup"><span data-stu-id="35abd-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="35abd-105">Klicken Sie auf dem Bildschirm Hauptelemente der Konfiguration **zu aktualisieren** , um zu aktualisieren und erneutes Auffüllen die Liste der Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="35abd-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="35abd-106">Ein Suchfeld wird zum Einschränken der Liste der angezeigten Richtlinien bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="35abd-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="35abd-107">Während der Eingabe des Namens, dem Sie für Durchsuchen wird automatisch die Liste der Richtlinien eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="35abd-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="35abd-p102">Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="35abd-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="35abd-111">Es sind zwei Auswahlmöglichkeiten für die Richtlinie für die Erstellung und Bearbeitung zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="35abd-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="35abd-112">**Neu**: Klicken Sie zum Erstellen einer neuen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="35abd-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="35abd-113">Geben Sie eine Website für die Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="35abd-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="35abd-114">Sie konfigurieren, klicken Sie dann die Einstellungen für die Pushbenachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="35abd-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="35abd-115">**Pushbenachrichtigungskonfiguration**können Sie nur Richtlinien für Websites erstellen, die Sie bereits erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="35abd-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="35abd-116">**Bearbeiten**: Wählen Sie eine Richtlinie aus, und klicken Sie auf Bearbeiten, um eine Aktion in einem Dropdown-Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="35abd-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="35abd-117">Sie können Websites nur, dass Sie bereits erstellt haben, oder bearbeiten die globale Richtlinie bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="35abd-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
  - <span data-ttu-id="35abd-118">**Details anzeigen**: Zeigt Informationen über die aktuell ausgewählten Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="35abd-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="35abd-119">Sie werden können so ändern Sie die vorhandene Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="35abd-119">You will be able to make changes to the existing policy.</span></span>
    
  - <span data-ttu-id="35abd-120">**Wählen Sie alle**: Wenn Sie eine von Richtlinien Anzahl und alle Richtlinien auswählen möchten, klicken Sie auf Alles markieren</span><span class="sxs-lookup"><span data-stu-id="35abd-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
  - <span data-ttu-id="35abd-121">**Löschen**: die ausgewählte Richtlinie entfernt.</span><span class="sxs-lookup"><span data-stu-id="35abd-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="35abd-122">Mithilfe von **Alles markieren** und **Löschen** werden alle Richtlinien entfernt.</span><span class="sxs-lookup"><span data-stu-id="35abd-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35abd-123">Die Standardrichtlinie **Global** kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="35abd-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="35abd-124">Wenn Sie versuchen, ihn zu löschen, werden Sie benachrichtigt, dass die globale Richtlinie auf die Standardwerte zurückgegeben wurde (d. h., alle Einstellungen werden deaktiviert), aber die Richtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="35abd-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="35abd-125">Eine neue Richtlinie erstellen oder Bearbeiten einer vorhandenen Richtlinie gibt es zwei Aktionen:</span><span class="sxs-lookup"><span data-stu-id="35abd-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="35abd-126">**Commit ausführen** Dieser Aktion erstellt oder aktualisiert die Richtlinie und speichert die Änderungen</span><span class="sxs-lookup"><span data-stu-id="35abd-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="35abd-127">**Abbrechen** Die Aktion abbrechen verwirft alle Änderungen, die seit der letzten Commit-Aktion vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="35abd-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="35abd-128">Wenn Sie abbrechen möchten, gehen alle vorgenommenen Änderungen verloren.</span><span class="sxs-lookup"><span data-stu-id="35abd-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="35abd-129">Es sind zwei Einstellungen für **Pushbenachrichtigungskonfiguration**möglich.</span><span class="sxs-lookup"><span data-stu-id="35abd-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="35abd-130">Die Einstellungen sind der Push-Notification-Services für Microsoft und Apple zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="35abd-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="35abd-131">Aktivieren Sie Pushbenachrichtigungen für einen der Dienste, indem Sie das Kontrollkästchen neben dem Namen des Diensts auswählen.</span><span class="sxs-lookup"><span data-stu-id="35abd-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="35abd-132">Sie können das Kontrollkästchen deaktivieren, indem Sie ihn deaktivieren sie die Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="35abd-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="35abd-133">Nachdem Sie Ihre Auswahl getroffen haben, Sie entweder einen commit oder abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="35abd-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="35abd-134">Klicken Sie dann auf Commit wird die Änderungen an der Richtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="35abd-134">Clicking commit will save the changes to the policy.</span></span>
  

