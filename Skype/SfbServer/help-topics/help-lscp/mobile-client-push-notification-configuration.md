---
title: Push-Benachrichtigungskonfiguration für mobile Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Wenn Sie die Microsoft Push-Benachrichtigungen und Apple Push-Benachrichtigungen konfigurieren möchten, müssen Sie eine Richtlinie erstellen, um festzulegen, welche Arten von Push-Benachrichtigungen Sie benötigen.
ms.openlocfilehash: 3fde99c3f026f87197492417cd10611d96f7e20e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822658"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="bbb21-103">Mobiler Client: Konfiguration für Pushbenachrichtigung</span><span class="sxs-lookup"><span data-stu-id="bbb21-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="bbb21-104">Wenn Sie die **Microsoft Push-Benachrichtigungen** und **Apple Push-Benachrichtigungen**konfigurieren möchten, müssen Sie eine Richtlinie erstellen, um festzulegen, welche Arten von Push-Benachrichtigungen Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="bbb21-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="bbb21-105">Auf dem Hauptbildschirm der Konfiguration können Sie auf **Aktualisieren** klicken, um die Liste der Richtlinien zu aktualisieren und neu zu füllen.</span><span class="sxs-lookup"><span data-stu-id="bbb21-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="bbb21-106">Ein Suchfeld wird zum Einschränken der Liste der angezeigten Richtlinien bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="bbb21-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="bbb21-107">Wenn Sie den gesuchten Namen eingeben, wird die Liste der Richtlinien automatisch eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="bbb21-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bbb21-p102">Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="bbb21-p102">Policy settings that are applied at one policy level can override settings that are applied at another policy level. Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence). This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="bbb21-111">Für die Richtlinienerstellung und-Bearbeitung stehen zwei Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="bbb21-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="bbb21-112">**Neu**: Klicken Sie hier, um eine neue Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bbb21-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="bbb21-113">Sie müssen eine Website angeben, auf die die Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bbb21-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="bbb21-114">Anschließend konfigurieren Sie die Einstellungen für die Push-Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="bbb21-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="bbb21-115">Für die **Konfiguration der Push-Benachrichtigung**können Sie nur Richtlinien für Websites erstellen, die Sie bereits erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="bbb21-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="bbb21-116">**Bearbeiten**: Wählen Sie eine Richtlinie aus, und klicken Sie auf Bearbeiten, um eine Aktion aus einer Dropdownliste auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="bbb21-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="bbb21-117">Sie können nur Websites bearbeiten, die Sie bereits erstellt haben, oder die globale Richtlinie bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="bbb21-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="bbb21-118">**Details anzeigen**: zeigt Informationen zur aktuell ausgewählten Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="bbb21-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="bbb21-119">Sie werden in der Lage sein, Änderungen an der vorhandenen Richtlinie vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="bbb21-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="bbb21-120">**Alle auswählen**: Wenn Sie über eine Reihe von Richtlinien verfügen und alle Richtlinien auswählen müssen, klicken Sie auf alle auswählen.</span><span class="sxs-lookup"><span data-stu-id="bbb21-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="bbb21-121">**Löschen**: entfernt die ausgewählte Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="bbb21-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="bbb21-122">Durch Verwenden von **"Alles auswählen" und "** **Löschen** " werden alle Richtlinien entfernt</span><span class="sxs-lookup"><span data-stu-id="bbb21-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="bbb21-123">Sie können die standardmäßige **globale** Richtlinie nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="bbb21-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="bbb21-124">Wenn Sie versuchen, Sie zu löschen, werden Sie darauf hingewiesen, dass die globale Richtlinie an die Standardwerte zurückgegeben wurde (das heißt, alle Einstellungen werden gelöscht), aber die Richtlinie kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="bbb21-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="bbb21-125">Das Erstellen einer neuen Richtlinie oder das Bearbeiten einer vorhandenen Richtlinie ist mit zwei Aktionen verknüpft:</span><span class="sxs-lookup"><span data-stu-id="bbb21-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="bbb21-126">**Commit** Die Commit-Aktion erstellt oder aktualisiert die Richtlinie und speichert die Änderungen</span><span class="sxs-lookup"><span data-stu-id="bbb21-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="bbb21-127">**Abbrechen** Mit der Aktion Cancel werden alle Änderungen verworfen, die seit der letzten Commit-Aktion vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="bbb21-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="bbb21-128">Wenn Sie kündigen, gehen die vorgenommenen Änderungen verloren.</span><span class="sxs-lookup"><span data-stu-id="bbb21-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="bbb21-129">Für die **Konfiguration der Push-Benachrichtigung**sind zwei Einstellungen möglich.</span><span class="sxs-lookup"><span data-stu-id="bbb21-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="bbb21-130">Die Einstellungen sind den Push Notification Services für Microsoft und für Apple zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="bbb21-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="bbb21-131">Sie aktivieren die Push-Benachrichtigung für beide Dienste, indem Sie das Kontrollkästchen neben dem Namen des Diensts aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bbb21-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="bbb21-132">Sie können das Kontrollkästchen deaktivieren, indem Sie es auswählen, um es zu löschen.</span><span class="sxs-lookup"><span data-stu-id="bbb21-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="bbb21-133">Nachdem Sie Ihre Auswahl getroffen haben, müssen Sie entweder committen oder stornieren.</span><span class="sxs-lookup"><span data-stu-id="bbb21-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="bbb21-134">Durch Klicken auf Commit werden die Änderungen an der Richtlinie gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bbb21-134">Clicking commit will save the changes to the policy.</span></span>
  

