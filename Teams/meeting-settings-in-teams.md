---
title: Verwalten von Besprechungseinstellungen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.overview
MS.collection: Teams_ITAdmin_Help
description: Informationen Sie zum Verwalten von Einstellungen für Teams Besprechungen, die Benutzer in Ihrer Organisation planen.
ms.openlocfilehash: e4eba5f585f7621add95101d06194bebead507e2
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754417"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="f2420-103">Verwalten von Besprechungseinstellungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2420-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="f2420-104">Verwenden Sie als Administrator Teams Besprechungen Einstellungen Kontrolle, ob anonyme Benutzer teilnehmen an Besprechungen Teams, besprechungseinladungen anpassen, und wenn Sie Quality of Service (QoS) aktivieren möchten Festlegen von Ports für den Datenverkehr in Echtzeit können.</span><span class="sxs-lookup"><span data-stu-id="f2420-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set ports for real-time traffic.</span></span> <span data-ttu-id="f2420-105">Diese Einstellungen gelten für alle Besprechungen von Teams, Zeitplan für Benutzer in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f2420-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="f2420-106">Verwalten Sie diese Einstellungen von **Besprechungen** > **besprechungseinstellungen** in der Verwaltungskonsole von Microsoft-Teams.</span><span class="sxs-lookup"><span data-stu-id="f2420-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span> 

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="f2420-107">Zulassen, dass anonyme Benutzer an Besprechungen teilnehmen</span><span class="sxs-lookup"><span data-stu-id="f2420-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="f2420-108">Mit anonyme Teilnahme kann jeder die Besprechung als anonymer Benutzer teilnehmen, indem Sie auf den Link in der Einladung.</span><span class="sxs-lookup"><span data-stu-id="f2420-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> 

<span data-ttu-id="f2420-109">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="f2420-109">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="f2420-110">Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **besprechungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="f2420-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="f2420-111">Aktivieren Sie unter **Teilnehmer** **anonyme Benutzer können an einer Besprechung teilnehmen**.</span><span class="sxs-lookup"><span data-stu-id="f2420-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span> 

    <span data-ttu-id="f2420-112">![Meeting-Einstellungen-participants.png] (media/meeting-settings-participants.png "Screenshot der Teilnehmer Einstellungen für Teams Besprechungen in der Verwaltungskonsole von Microsoft-Teams")</span><span class="sxs-lookup"><span data-stu-id="f2420-112">![meeting-settings-participants.png](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="f2420-113">Wenn Sie nicht, dass anonyme Benutzern die Teilnahme von Benutzern in Ihrer Organisation geplant möchten, deaktivieren Sie diese Einstellung.</span><span class="sxs-lookup"><span data-stu-id="f2420-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span> 

## <a name="customize-meeting-invitations"></a><span data-ttu-id="f2420-114">Anpassen von Besprechungseinladungen</span><span class="sxs-lookup"><span data-stu-id="f2420-114">Customize meeting invitations</span></span>

<span data-ttu-id="f2420-115">Sie können Teams Besprechungsanfragen erfüllen der Anforderungen Ihrer Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="f2420-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="f2420-116">Sie können Ihrer Organisation Logo und enthalten hilfreiche Informationen, wie Links zu Support-Website und Haftungsausschluss und eine nur-Text-Fußzeile.</span><span class="sxs-lookup"><span data-stu-id="f2420-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span> 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="f2420-117">Tipps zum Erstellen eines Logos für Besprechungseinladungen</span><span class="sxs-lookup"><span data-stu-id="f2420-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="f2420-118">Erstellen Sie ein Bild, das nicht mehr als 188 Pixel breit und 30 Pixel hoch ist (es ist sehr klein).</span><span class="sxs-lookup"><span data-stu-id="f2420-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span> 
2. <span data-ttu-id="f2420-119">Speichern Sie das Bild im JPG-Format.</span><span class="sxs-lookup"><span data-stu-id="f2420-119">Save the image in JPG format.</span></span> 
3. <span data-ttu-id="f2420-120">Speichern Sie das Bild in einen zentralen Speicherort, den alle Benutzer in Ihrer Organisation, wie etwa einer Netzwerkfreigabe zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="f2420-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span> 

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="f2420-121">Anpassen der besprechungseinladungen</span><span class="sxs-lookup"><span data-stu-id="f2420-121">Customize your meeting invitations</span></span>

<span data-ttu-id="f2420-122">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="f2420-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f2420-123">Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **besprechungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="f2420-123">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="f2420-124">Führen Sie unter **E-Mail-Einladung**folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f2420-124">Under **Email invitation**, do the following:</span></span> 

    <span data-ttu-id="f2420-125">![Meeting-Einstellungen-invitation.png] (media/meeting-settings-invitation.png "Screenshot der Besprechung Einladung Einstellungen, die Sie für Teams Besprechungen anpassen können")</span><span class="sxs-lookup"><span data-stu-id="f2420-125">![meeting-settings-invitation.png](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span> 

    - <span data-ttu-id="f2420-126">**Logo-URL** Geben Sie die URL ein, in dem Ihr Logo gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f2420-126">**Logo URL** Enter the URL where your logo is stored.</span></span> 
    - <span data-ttu-id="f2420-127">**Rechtliche URL** Wenn Ihre Organisation rechtliche-Website, die Benutzern verfügt So wechseln zur für alle Probleme werden sollen, geben Sie die URL hier.</span><span class="sxs-lookup"><span data-stu-id="f2420-127">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span> 
    - <span data-ttu-id="f2420-128">**Hilfe-URL** Wenn Ihre Organisation eine Support-Website, die Benutzern verfügt zu wechseln, wenn sie Probleme ausgeführt werden soll, geben Sie die URL hier.</span><span class="sxs-lookup"><span data-stu-id="f2420-128">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="f2420-129">**Fußzeile** Geben Sie Text ein, den Sie als Footer einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="f2420-129">**Footer** Enter text that you want to include as a footer.</span></span> 
3. <span data-ttu-id="f2420-130">Warten Sie eine Stunde oder, damit die Änderungen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="f2420-130">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="f2420-131">Klicken Sie dann Planen einer Besprechung Teams finden in die Einladung zur Besprechung aussieht.</span><span class="sxs-lookup"><span data-stu-id="f2420-131">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="f2420-132">Legen Sie wie Real-Time Media-Datenverkehr für Teams Besprechungen behandelt werden sollen</span><span class="sxs-lookup"><span data-stu-id="f2420-132">Set how you want to handle real-time media traffic for Teams meetings</span></span>
<span data-ttu-id="f2420-133">Wenn Sie den Netzwerkverkehr zu priorisieren Quality of Service (QoS) verwenden, können Sie QoS-Markierung aktivieren, und Sie können Portbereiche für jede Art von Mediendatenverkehr festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2420-133">If you're using Quality of Service (QoS) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span> 

 <span data-ttu-id="f2420-134">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**</span><span class="sxs-lookup"><span data-stu-id="f2420-134">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f2420-135">Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **besprechungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="f2420-135">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="f2420-136">Führen Sie unter **Netzwerk**folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f2420-136">Under **Network**, do the following:</span></span>

    <span data-ttu-id="f2420-137">![Meeting-Einstellungen-network.png] (media/meeting-settings-network.png "Screenshot der Netzwerkeinstellungen für Teams Besprechungen in der Verwaltungskonsole von Microsoft-Teams")</span><span class="sxs-lookup"><span data-stu-id="f2420-137">![meeting-settings-network.png](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="f2420-138">Um QoS-Markierung aktivieren, aktivieren Sie **Einfügen Quality of Service (QoS)-Marker für Mediendatenverkehr in Echtzeit**.</span><span class="sxs-lookup"><span data-stu-id="f2420-138">To enable QoS markers, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span>
    - <span data-ttu-id="f2420-139">Um anzugeben Portbereiche neben, **Wählen Sie einen Portbereich für jede Art von Mediendatenverkehr in Echtzeit**, wählen Sie **Portbereiche angeben**und geben Sie die Start- und Enddatum Ports für Audio, Video und Bildschirmfreigabe.</span><span class="sxs-lookup"><span data-stu-id="f2420-139">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> 
    
        <span data-ttu-id="f2420-140">Wenn Sie wählen Sie **automatisch alle verfügbaren Ports verwenden**, verfügbaren Ports zwischen 1024 und 65535 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2420-140">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> 

 ### <a name="related-topics"></a><span data-ttu-id="f2420-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f2420-141">Related topics</span></span>
- [<span data-ttu-id="f2420-142">Quality of Service (QoS) in Teams</span><span class="sxs-lookup"><span data-stu-id="f2420-142">Quality of Service (QoS) in Teams</span></span>](qos-in-teams.md)

