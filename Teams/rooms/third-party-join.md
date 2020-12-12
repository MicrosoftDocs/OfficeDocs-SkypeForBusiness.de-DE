---
title: Aktivieren von "Teams Rooms"-Geräten für die Teilnahme an Besprechungen von Drittanbietern
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: In diesem Artikel wird beschrieben, wie Sie Ihre Organisations-und teamsräume-Geräte für die Unterstützung von Besprechungen von Drittanbietern in Cisco WebEx und Zoom konfigurieren.
ms.openlocfilehash: 8079b6fc231bf30a654e2513af55a806433eb83f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662360"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="f9f45-103">Aktivieren von Team Room-Geräten für die Teilnahme an Besprechungen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="f9f45-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="f9f45-104">Microsoft Teams rooms-Geräte unterstützen ein einmaliges Erlebnis für die Teilnahme an Onlinebesprechungen von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="f9f45-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings.</span></span> <span data-ttu-id="f9f45-105">Wenn diese Option aktiviert ist, können Sie ein Gerät für teamsräume verwenden, um an Besprechungen teilzunehmen, die auf Cisco WebEx und Zoom<sup>1</sup> gehostet werden, genauso einfach wie Sie an Besprechungen teilnehmen, die in Microsoft Teams gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="f9f45-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom<sup>1</sup> just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="f9f45-106">Bevor Sie von einem Team Room-Gerät an Drittanbieter Besprechungen teilnehmen können, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="f9f45-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="f9f45-107">Konfigurieren des Exchange Online Room-Postfachs des Teams rooms für die Verarbeitung von Einladungen für Besprechungen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="f9f45-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings</span></span>
2. <span data-ttu-id="f9f45-108">Stellen Sie sicher, dass Ihre Organisation keine Richtlinien enthält, die verhindern, dass Sie eine Verbindung mit den Besprechungs Diensten von Drittanbietern herstellen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services</span></span>
3. <span data-ttu-id="f9f45-109">Konfigurieren Sie Ihre Teams rooms-Geräte, um Besprechungen von Drittanbietern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-109">Configure your Teams Rooms devices to allow third-party meetings</span></span>

<span data-ttu-id="f9f45-110">In den folgenden Abschnitten wird erläutert, wie Sie die einzelnen Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="f9f45-111">Schritt 1: genehmigen der Kalender Einladungs Verarbeitung für Besprechungen von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="f9f45-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="f9f45-112">Das erste, was Sie tun müssen, um ein One-Touch-Join-Erlebnis von einem Team Room-Gerät zu aktivieren, ist die Kalender Verarbeitungsregeln für das Exchange Online Room-Postfach des Geräts festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="f9f45-113">Das Raumpostfach muss externe Besprechungen zulassen und den Nachrichtentext und das Thema beibehalten, damit die URL angezeigt wird, die für die Teilnahme an der Besprechung des Drittanbieters erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f9f45-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="f9f45-114">Gehen Sie wie folgt vor, um diese Raum Postfachoptionen mit dem Cmdlet " [CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) " zu definieren:</span><span class="sxs-lookup"><span data-stu-id="f9f45-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="f9f45-115">Stellen Sie eine Verbindung mit Exchange Online PowerShell her.</span><span class="sxs-lookup"><span data-stu-id="f9f45-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="f9f45-116">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell mit Standardauthentifizierung](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) oder [Herstellen einer Verbindung mit Exchange Online PowerShell mithilfe der mehr](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)stufigen Authentifizierung, je nach Ihrer Authentifizierungsmethode.</span><span class="sxs-lookup"><span data-stu-id="f9f45-116">For more information, see [Connect to Exchange Online Powershell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="f9f45-117">Rufen Sie den Benutzerprinzipalnamen (User Principal Name, UPN) des Room-Postfachs ab, wenn Sie ihn nicht kennen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="f9f45-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. <span data-ttu-id="f9f45-118">Suchen Sie den Namen des Raumpostfachs, das mit dem Gerät Ihres Teams rooms verknüpft ist, und notieren Sie sich dessen UPN.</span><span class="sxs-lookup"><span data-stu-id="f9f45-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN</span></span>

4. <span data-ttu-id="f9f45-119">Nachdem Sie den UPN des Room-Postfachs gefunden haben, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="f9f45-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="f9f45-120">Ersetzen Sie dies `<UserPrincipalName>` durch den UPN des Room-Postfachs:</span><span class="sxs-lookup"><span data-stu-id="f9f45-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="f9f45-121">Weitere Informationen zu [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="f9f45-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="f9f45-122">Schritt 2: Konfigurieren von Office 365-Bedrohungsschutz und erneutem Erstellen von Links</span><span class="sxs-lookup"><span data-stu-id="f9f45-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="f9f45-123">Zum Aktivieren der einmaligen Verknüpfungsfunktion müssen Besprechungs Verknüpfungsinformationen aus der Drittanbieter Besprechung in der Besprechungseinladung vorhanden und lesbar sein.</span><span class="sxs-lookup"><span data-stu-id="f9f45-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="f9f45-124">Wenn in Ihrer Organisation das Feature " [Erweiterter Bedrohungsschutz" von Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) verwendet wird oder wenn Sie eine Lösung eines Drittanbieters verwenden, die alle eingehenden und ausgehenden URLs auf Bedrohungen scannt, kann Sie die URLs der Besprechungsteilnahme ändern und die Besprechung vom Gerät "Teams Rooms" unkenntlich machen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="f9f45-125">Um sicherzustellen, dass dies nicht der Fall ist, müssen Sie die URLs des Drittanbieters des Besprechungs Diensts der ATP-Liste der sicheren Links "nicht umschreiben" oder der Ausnahmeliste für URL-Umschreibungen von Drittanbietern hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="f9f45-126">Zum Hinzufügen von Drittanbieter-Besprechungs Dienst-URLs zu den ATP-Sicherheits Links "nicht umschreiben" führen Sie die Schritte unter [Einrichten einer benutzerdefinierten URL-Liste "nicht umschreiben" mithilfe von ATP-Sicherheits Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)aus.</span><span class="sxs-lookup"><span data-stu-id="f9f45-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="f9f45-127">Wenn Sie eine Lösung eines Drittanbieters verwenden, lesen Sie die Anweisungen für diese Lösung, um URLs zur Ausnahmeliste für URL-Umschreibungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="f9f45-128">Nachfolgend sind einige Beispieleinträge aufgeführt, die Sie möglicherweise zu ihren ATP-Sicherheits Links "nicht umschreiben" oder der Ausnahmeliste für URL-Umschreibungen von Drittanbietern hinzufügen müssen:</span><span class="sxs-lookup"><span data-stu-id="f9f45-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="f9f45-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="f9f45-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="f9f45-130">**Zoom** `*.zoom.us*` , `*.zoom.com*` , `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="f9f45-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="f9f45-131">Eine vollständige Liste der URLs, die Sie zu ihren ATP-sicheren Links "nicht umschreiben"-Liste oder zur Ausnahmeliste eines Drittanbieters für URL-Umschreibungen hinzufügen können, erhalten Sie vom Drittanbieter-Besprechungs Dienstanbieter, von dem Sie Besprechungseinladungen annehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="f9f45-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="f9f45-132">Fügen Sie nur URLs, denen Sie Vertrauen, zu ihren ATP-sicheren Links "nicht umschreiben"-Liste oder Ausnahmeliste für URL-Umschreibungen von Drittanbietern hinzu.</span><span class="sxs-lookup"><span data-stu-id="f9f45-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="f9f45-133">Schritt 3: Aktivieren von Besprechungen von Drittanbietern auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="f9f45-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="f9f45-134">Der letzte Schritt besteht darin, das Gerät für die einzelnen Teams für die Teilnahme an Besprechungen von Drittanbietern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="f9f45-135">Für Besprechungen von Drittanbietern müssen Sie einen Benutzernamen und eine e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="f9f45-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="f9f45-136">Wenn der Benutzername und die e-Mail-Adresse, die Sie verwenden müssen, anders als das Raumpostfach des Geräts sind, müssen Sie Sie auf Ihrem Gerät hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="f9f45-137">Dies können Sie in den Geräteeinstellungen oder in der XML-Konfigurationsdatei vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="f9f45-138">Verwenden von Geräteeinstellungen</span><span class="sxs-lookup"><span data-stu-id="f9f45-138">Use device settings</span></span>

<span data-ttu-id="f9f45-139">Gehen Sie wie folgt vor, um das Gerät "Teams Rooms" über seinen Touchscreen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f9f45-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="f9f45-140">Wählen Sie auf dem Gerät Microsoft Teams rooms den Eintrag **mehr...**</span><span class="sxs-lookup"><span data-stu-id="f9f45-140">On the Microsoft Teams Rooms device, select **More ...**</span></span>
2. <span data-ttu-id="f9f45-141">Wählen Sie **Einstellungen** aus, und geben Sie dann den Benutzernamen und das Kennwort für den Geräteadministrator ein.</span><span class="sxs-lookup"><span data-stu-id="f9f45-141">Select **Settings**, and then enter the device administrator username and password</span></span>
3. <span data-ttu-id="f9f45-142">Wechseln Sie zur Registerkarte **Besprechungen** , und wählen Sie **Cisco WebEx**, **Zoom**<sup>1</sup>oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="f9f45-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**<sup>1</sup>, or both</span></span>
4. <span data-ttu-id="f9f45-143">Wenn Sie mit dem Benutzernamen und der e-Mail-Adresse, die dem Raumpostfach zugeordnet ist, an Besprechungen teilnehmen möchten, wählen Sie **mit Rauminformationen beitreten** aus.</span><span class="sxs-lookup"><span data-stu-id="f9f45-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**</span></span>
5. <span data-ttu-id="f9f45-144">Wenn Sie mit einem alternativen Benutzernamen und einer e-Mail-Adresse an Besprechungen teilnehmen möchten, wählen Sie **mit benutzerdefinierten Informationen beitreten** aus, und geben Sie den Benutzernamen und die e-Mail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="f9f45-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use</span></span>
6. <span data-ttu-id="f9f45-145">Wählen Sie **Speichern und beenden** aus.</span><span class="sxs-lookup"><span data-stu-id="f9f45-145">Select **Save and exit**.</span></span> <span data-ttu-id="f9f45-146">Ihr Gerät wird neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="f9f45-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="f9f45-147">Verwenden der SkypeSettings.xml-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="f9f45-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="f9f45-148">Die folgenden Einstellungen können zu der Datei hinzugefügt werden, die `SkypeSettings.xml` sich in befindet `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` .</span><span class="sxs-lookup"><span data-stu-id="f9f45-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="f9f45-149">Weitere Informationen zur `SkypeSettings.xml` Datei finden Sie unter [Verwalten von Microsoft Teams rooms-Konsoleneinstellungen Remote mit einer XML-Konfigurationsdatei](xml-config-file.md).</span><span class="sxs-lookup"><span data-stu-id="f9f45-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="f9f45-150">Um Cisco WebEx-Besprechungen zu aktivieren, `WebExMeetingsEnabled` müssen Sie das XML-Element wie folgt auf " **true**" festlegen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="f9f45-151">Um Zoom <sup>1</sup> -Besprechungen zu aktivieren, `ZoomMeetingsEnabled` müssen Sie das XML-Element wie folgt auf " **true**" festlegen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-151">To enable Zoom <sup>1</sup> meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="f9f45-152">Optional können Sie einen benutzerdefinierten Benutzernamen und eine e-Mail-Adresse angeben, um mit den folgenden XML-Elementen an Besprechungen von Drittanbietern teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f9f45-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="f9f45-153">Wenn die von Ihnen bereitgestellten Werte nicht gültig sind, verwendet das Gerät "Teams Rooms" standardmäßig den Benutzernamen und die e-Mail-Adresse für Room Mailbox.</span><span class="sxs-lookup"><span data-stu-id="f9f45-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="f9f45-154">Wenn Sie von einem Team Room-Gerät aus an Cisco WebEx-Besprechung teilnehmen möchten, muss die Cisco-Besprechung mit der Cisco WebEx Web Application-Version PSP 40,7 oder höher gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="f9f45-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

<span data-ttu-id="f9f45-155"><sup>1</sup> Zoom-Besprechungsteilnahme ist derzeit nur verfügbar, um Microsoft Teams rooms-Kunden über das Technologie Zugriffs Programm auszuwählen (tippen).</span><span class="sxs-lookup"><span data-stu-id="f9f45-155"><sup>1</sup> Zoom meetings join is currently only available to select Microsoft Teams Rooms customers through Technology Access Program (TAP).</span></span>
