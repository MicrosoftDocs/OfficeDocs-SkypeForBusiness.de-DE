---
title: Verwalten von Besprechungsrichtlinien für Audio und Video
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Besprechungsrichtlinieneinstellungen in Teams für Audio und Video verwalten.
ms.openlocfilehash: ac5c58c00f5069638c087d04a033e8e0ff3d4822
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706845"
---
# <a name="meeting-policy-settings-for-audio--video"></a>Besprechungsrichtlinieneinstellungen für Audio& Video

<a name="bkaudioandvideo"> </a>
<a name="ndi"> </a>

In diesem Artikel werden die Besprechungsrichtlinieneinstellungen für Audio und Video beschrieben. Diese beinhalten Folgendes:

- [Modus für IP-Audio](#mode-for-ip-audio)
- [Modus für IP-Video](#mode-for-ip-video)
- [IP-Video](#ip-video)
- [Media-Bitrate (KBs)](#media-bit-rate-kbs)
- [Videofiltermodus](#video-filters-mode)
- [Benutzerdefinierte Hintergrundeinstellungen zulassen](#allow-custom-background-settings)
- [Far End Camera Control (FECC) für PTZ-Kameras (Point Tilt Zoom)](#far-end-camera-control-fecc-for-point-tilt-zoom-ptz-cameras)

### <a name="mode-for-ip-audio"></a>Modus für IP-Audio

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Audio in Besprechungen und Gruppenanrufen aktiviert werden kann. Nachfolgend sind die Werte für diese Einstellung aufgeführt.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Ausgehendes und eingehendes Audio aktiviert**    |Ausgehendes und eingehendes Audio ist in der Besprechung zulässig. Dies ist die Standardeinstellung. |
|**Nicht aktiviert**     |Ausgehendes und eingehendes Audio ist in der Besprechung deaktiviert.     |

Wenn diese Einstellung für einen Benutzer auf **"Nicht aktiviert** " festgelegt ist, kann dieser Benutzer Besprechungen zwar planen und organisieren, aber keine Audiodaten verwenden. Wenn er an einer Besprechung teilnehmen möchte, muss er sich über das öffentliche Festnetz einwählen, oder sich aus der Besprechung anrufen lassen und per Telefon daran teilnehmen. Für Besprechungsteilnehmer, denen keine Richtlinien zugewiesen sind (z. B. anonyme Teilnehmer), ist diese Einstellung standardmäßig auf **Ausgehendes und eingehendes Audio aktiviert** festgelegt. Wenn diese Einstellung auf mobilen Teams-Clients nicht aktiviert ist, muss sich der Benutzer über das PSTN in die Besprechung einwählen.

Diese Einstellung gilt nicht für Einzelanrufe. Wenn Sie Einzelanrufe einschränken möchten, konfigurieren Sie eine Microsoft Teams-[Anrufrichtlinie](teams-calling-policy.md), und deaktivieren Sie die Einstellung für das Tätigen **privater Anrufe**. Diese Einstellung gilt auch nicht für Konferenzraumgeräte wie Surface Hub und Geräte für Microsoft Teams-Räume.

Diese Einstellung ist noch nicht für die Microsoft 365 Government Community Cloud (GCC), GCC High- und DoD-Umgebungen (Department of Defense) verfügbar.

Weitere Informationen hierzu finden Sie unter [Audio/Video für Besprechungsteilnehmer verwalten](#manage-audiovideo-for-meeting-participants).

### <a name="mode-for-ip-video"></a>Modus für IP-Video

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Video in Besprechungen und Gruppenanrufen aktiviert werden kann. Nachfolgend sind die Werte für diese Einstellung aufgeführt.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Ausgehendes und eingehendes Video aktiviert**    | Ausgehendes und eingehendes Video ist in der Besprechung zulässig. Dies ist die Standardeinstellung. |
|**Nicht aktiviert**     | Ausgehendes und eingehendes Video ist in der Besprechung deaktiviert. Auf mobilen Microsoft Teams-Clients können Benutzer keine Videos oder Fotos in der Besprechung freigeben. <br><br>Beachten Sie, dass der **Modus für IP-Audio** ebenfalls nicht aktiviert bleibt, wenn der **Modus für IP-Audio** nicht aktiviert ist.  |

Wenn diese Einstellung für einen Benutzer auf **"Nicht aktiviert** " festgelegt ist, kann dieser Benutzer keine Videos aktivieren oder anzeigen, die von anderen Besprechungsteilnehmern geteilt wurden. Für Besprechungsteilnehmer, denen keine Richtlinien zugewiesen sind (z. B. anonyme Teilnehmer), ist diese Einstellung standardmäßig auf **Ausgehendes und eingehendes Video aktiviert** festgelegt.

Diese Einstellung gilt nicht für Konferenzraumgeräte wie Surface Hub und Geräte für Microsoft Teams-Räume.

Diese Einstellung ist noch nicht für die Microsoft 365 Government Community Cloud (GCC), GCC High- und DoD-Umgebungen (Department of Defense) verfügbar.

> [!NOTE]
> Beachten Sie, dass diese Einstellung sowohl ausgehendes als auch eingehendes Video steuert, während die **IP-Videoeinstellung** ausgehendes Video steuert. Weitere Informationen hierzu finden Sie unter [Welche IP-Videorichtlinieneinstellung hat Vorrang?](#which-ip-video-policy-setting-takes-precedence) und [Audio/Video für Besprechungsteilnehmer verwalten](#manage-audiovideo-for-meeting-participants).

Weitere Informationen hierzu finden Sie unter [Audio/Video für Besprechungsteilnehmer verwalten](#manage-audiovideo-for-meeting-participants).

### <a name="ip-video"></a>IP-Video

Hierbei handelt es sich um eine Kombination aus einer benutzerspezifischen und einer organisatorspezifischen Richtlinie. Die Videofunktion ist ein Schlüsselelement in Besprechungen. In einigen Organisationen möchten Administratoren möglicherweise mehr Kontrolle darüber haben, in welchen Besprechungen der Benutzer Video genutzt werden kann. Über diese Einstellung wird gesteuert, ob Video in von einem Benutzer gehosteten Besprechungen oder in von einem Benutzer gestarteten Einzel- und Gruppenanrufen eingeschaltet werden kann. Auf mobilen Teams-Clients steuert diese Einstellung, ob Benutzer Fotos und Videos in einer Besprechung freigeben können.

In Besprechungen, die von einem Benutzer organisiert wurden, für den diese Richtlinieneinstellung aktiviert ist, ist die Videofreigabe durch die Teilnehmer zulässig, sofern die Richtlinieneinstellung für sie ebenfalls aktiviert ist. Besprechungsteilnehmer, denen keine Richtlinien zugewiesen sind (z. B. anonyme Teilnehmer und Partner), erben die für den Besprechungsorganisator geltende Richtlinie.

> [!NOTE]
> Beachten Sie, dass über diese Einstellung ausgehendes Video gesteuert wird, während über die Einstellung für den **Modus für IP-Video** sowohl eingehendes als auch ausgehendes Video gesteuert wird. Weitere Informationen hierzu finden Sie unter [Welche IP-Videorichtlinieneinstellung hat Vorrang?](#which-ip-video-policy-setting-takes-precedence) und [Audio/Video für Besprechungsteilnehmer verwalten](#manage-audiovideo-for-meeting-participants).

| Microsoft Teams – Desktop und Web-Client |Mobile Microsoft Teams-Clients  |
|:-------:|:-------:|
|![Screenshot zeigt die Besprechungsteilnahme mit Audio/Video-Einstellungen auf dem Desktop.](media/meeting-policies-audio-video-settings.png)    |![Screenshot der Besprechungsteilnahme-Seite mit Audio/Video-Einstellungen auf einem Mobilgerät](media/meeting-policies-mobile-join.png)          |

Sehen Sie sich das folgende Beispiel an.

|Benutzer |Besprechungsrichtlinie  |IP-Video |
|---------|---------|---------|
|Daniela   | Global   | Ein       |
|Amalia    | Location1MeetingPolicy        | Aus      |

In von Daniela organisierten Besprechungen kann die Videofunktion aktiviert werden. Daniela kann an der Besprechung teilnehmen und die Videofunktion aktivieren. Amanda kann die Videofunktion in Danielas Besprechung nicht aktivieren, da für sie die Richtlinie so festgelegt ist, dass Video nicht zulässig ist. Amanda kann Videos anzeigen, die von anderen Teilnehmern der Besprechung geteilt werden.

In Besprechungen, die von Amanda gehostet werden, kann unabhängig von der ihm zugewiesenen Videorichtlinie niemand die Videofunktion aktivieren. Das bedeutet, dass Daniela in Amandas Besprechungen die Videofunktion nicht aktivieren kann.  

Wenn Daniela Amanda bei aktivierter Videofunktion anruft, kann Amanda den Anruf nur mit Audio annehmen.  Bei laufendem Anruf kann Amanda Danielas Video sehen, selbst die Videofunkton jedoch nicht aktivieren. Wenn Amanda Daniela anruft, kann Daniela den Anruf mit Video und Audio annehmen. Bei laufendem Anruf kann Daniela ihr Video nach Wunsch aktivieren oder deaktivieren.

Weitere Informationen hierzu finden Sie unter [Audio/Video für Besprechungsteilnehmer verwalten](#manage-audiovideo-for-meeting-participants).

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>Welche IP-Videorichtlinieneinstellung hat Vorrang?

Für einen Benutzer hat die restriktivste Richtlinieneinstellung für Videos Vorrang. Hier sind einige Beispiele.

|IP-Video|Modus für IP-Video|Auswirkung|
|---------|---------|---------|
|Organisator: **Aktiviert**<br><br>Teilnehmer: **Aktiviert** |Teilnehmer: **Deaktiviert**        |Die Einstellung für den **Modus für IP-Video** hat Vorrang. Ein Teilnehmer, dem diese Richtlinie zugewiesen ist, kann die von anderen Personen freigegebenen Videos weder aktivieren noch anzeigen.|
|Organisator: **Aktiviert**<br><br>Teilnehmer: **Aktiviert** |Teilnehmer: **Ausgehendes und eingehendes Video aktiviert**          |Ein Teilnehmer, dem diese Richtlinie zugewiesen ist, kann von anderen Personen freigegebene Videos aktivieren und anzeigen.         |
|Organisator: **Aktiviert**<br><br>Teilnehmer: **Deaktiviert** |Teilnehmer: **Ausgehendes und eingehendes Video aktiviert**         |Die **IP-Videoeinstellung** hat Vorrang. Die Teilnehmer können nur eingehende Videos anzeigen und keine ausgehenden Videos senden.         |
|Organisator: **Aktiviert**<br><br>Teilnehmer: **Deaktiviert** |Teilnehmer: **Deaktiviert**         |Die Einstellung für den **Modus für IP-Video** hat Vorrang. Der Teilnehmer kann weder eingehende noch ausgehende Videos anzeigen.|
|Organisator: **Deaktiviert**    |       |Die **IP-Videoeinstellung** hat Vorrang, da sie für den Organisator deaktiviert ist. Niemand kann die Videofunktion in Besprechungen aktivieren, die von dem Benutzer organisiert wurden, dem diese Richtlinie zugewiesen wurde.         |

### <a name="manage-audiovideo-for-meeting-participants"></a>Audio/Video für Besprechungsteilnehmer verwalten

|Sie möchten ...  |Legen Sie die folgenden Richtlinieneinstellungen fest  |
|---------|---------|
|Audio und Video für Teilnehmer in Besprechungen deaktivieren  |Modus für IP-Audio: **Deaktiviert**<br> Modus für IP-Video: **Deaktiviert**<br>IP-Video: NV       |
|Nur eingehendes Video und Audio für Teilnehmer in Besprechungen aktivieren  |Modus für IP-Audio: **Ausgehendes und eingehendes Audio aktiviert**<br> Modus für IP-Video: **Ausgehendes und eingehendes Video aktiviert**<br>IP-Video: **Aus**       |
|Video für Teilnehmer in Besprechungen deaktivieren (für die Teilnehmer ist nur Audio verfügbar)|  Modus für IP-Audio: **Ausgehendes und eingehendes Audio aktivieren**<br> Modus für IP-Video: **Deaktiviert**<br>IP-Video: NV
|Audio und Video für Teilnehmer in Besprechungen aktivieren    |Modus für IP-Audio: **Ausgehendes und eingehendes Audio aktiviert** (Standard)<br> Modus für IP-Video: **Ausgehendes und eingehendes Video aktiviert** (Standard)<br>IP-Video: **Ein** (Standard)    |

Die restriktivste Richtlinie zwischen der Richtlinie des Besprechungsorganisators und jener des Benutzers hat Vorrang. Wenn für den Organisator beispielsweise eine Richtlinie gilt, die Video einschränkt, und die für den Benutzer geltende Richtlinie Video nicht einschränkt, erben Besprechungsteilnehmer die Richtlinie des Besprechungsorganisators und haben in Besprechungen keinen Zugriff auf die Videofunktion. Dies bedeutet, dass sie an der Besprechung nur per Audio teilnehmen können.

> [!NOTE]
> Wenn ein Benutzer einen Gruppenanruf startet, bei dem man über das Telefon teilnimmt, wird der Bildschirm **Telefon für Audio verwenden** nicht angezeigt. Dieses Problem ist bekannt, und wir arbeiten an einer Lösung. Um dieses Problem zu umgehen, wählen Sie **Telefon-Audio** unter **Andere Verbindungsoptionen** aus.

#### <a name="teams-mobile-clients"></a>Mobile Microsoft Teams-Clients

Für Benutzer auf mobilen Teams-Clients wird die Möglichkeit, Fotos und Videos während einer Besprechung freizugeben, auch durch die Einstellung des **IP-Video****- oder IP-Videomodus** bestimmt. Je nachdem, welche Richtlinieneinstellung Vorrang hat, ist die Option zum Teilen von Videos und Fotos nicht verfügbar. Dies wirkt sich nicht auf die Bildschirmfreigabe aus, die diese über eine eigene Einstellung für den [Bildschirmfreigabemodus](meeting-policies-content-sharing.md#screen-sharing-mode) konfiguriert wird. Darüber hinaus können Sie eine [Microsoft Teams-Richtlinie für Mobilgeräte](/powershell/module/skype/new-csteamsmobilitypolicy) festlegen, um zu verhindern, dass Benutzer von Mobilgeräten die IP-Videofunktion über eine Mobilverbindung verwenden; dies bedeutet, dass sie eine WLAN-Verbindung verwenden müssen.

### <a name="media-bit-rate-kbs"></a>Media-Bitrate (KBs)

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Diese Einstellung bestimmt für den Benutzer die Medienbitrate für Audio-, Video- und videobasierte App-Übertragung bei Anrufen und in Besprechungen. Sie wird sowohl auf die Uplink- als auch auf die Downlink-Medienübertragung für die Benutzer die sich in einem Anruf oder einer Besprechung befinden, angewendet. Mit dieser Einstellung können Sie die Bandbreite in Ihrer Organisation präzise kontrollieren und verwalten. Je nach Szenario, das die Benutzer benötigen, empfiehlt es sich, genügend Bandbreite für eine bereitzustellen, um eine gute, qualitativ hochwertige Erfahrung zu gewährleisten. Der Mindestwert beträgt 30 KBit/s. Der Höchstwert ist von der jeweiligen Besprechungssituation abhängig. Weitere Informationen zur empfohlenen Mindestbandbreite für Besprechungen, Anrufe und Live-Ereignisse in hoher Qualität in Microsoft Teams finden Sie unter [Bandbreitenanforderungen](prepare-network.md#bandwidth-requirements).

Wenn für eine Besprechung nicht genügend Bandbreite verfügbar ist, wird den Teilnehmern eine Nachricht angezeigt, die auf die geringe Übertragungsleistung hinweist.

Wenn Sie Besprechungen mit höchster Videoqualität, z. B. Vorstandssitzungen oder Microsoft Teams-Liveereignisse, organisieren wollen, empfehlen wir, die Bandbreite auf 10 Mbit/s festzulegen. Selbst wenn die Einstellungen für ein möglichst hochwertiges Ergebnis festgelegt wurden, passt sich der Microsoft Teams-Medienstack an die Bedingungen geringer Bandbreite an, wenn abhängig vom Szenario bestimmte Netzwerkbedingungen ermittelt wurden.

## <a name="video-filters-mode"></a>Videofiltermodus

<a name="bkvideofilters"> </a>

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Benutzer ihre Videohintergründe in einer Besprechung anpassen können.

Sie können sowohl das Teams Admin Center als auch PowerShell verwenden, um diese Richtlinie festzulegen. Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie dann Benutzern zuweisen.

Um anzugeben, ob Benutzer ihren Videohintergrund in einer Besprechung anpassen können, legen Sie den **Parameter "VideoFiltersMode** " (Einstellung "**Videofilter auswählen** " im Teams Admin Center) wie folgt fest:

|Festzulegender Wert in PowerShell|Festlegen des Werts im Teams Admin Center |Verhalten  |
|---------|---------|---------|
|**NoFilters** |**Kein Filter**    |Der Benutzer kann seinen Videohintergrund nicht anpassen.|
|**BlurOnly**     |**Nur Weichzeichner im Hintergrund**|Der Benutzer hat die Möglichkeit, den Hintergrund des Videos weichzuzeichnen. |
|**BlurandDefaultBackgrounds**|**Weichzeichner im Hintergrund und Standardbilder**     |Der Benutzer hat die Möglichkeit, den Hintergrund des Videos weichzuzeichnen oder eines der Standardbilder auszuwählen, die als Hintergrund verwendet werden können. |
|**AllFilters**|**Alle Filter**     |Der Benutzer hat die Möglichkeit, den Hintergrund des Videos weichzuzeichnen, eines der Standardbilder auszuwählen oder ein eigenes Bild hochzuladen, um es als Hintergrund zu verwenden. |

> [!NOTE]
> Bilder, die von Benutzern hochgeladen wurden, werden von Microsoft Teams nicht überprüft. Wenn Sie die Einstellung **AllFilters** verwenden, sollten Sie über interne Richtlinien für Ihre Organisation verfügen, um zu verhindern, dass Benutzer anstößige oder unangemessene Bilder hochladen oder solche, für die Ihre Organisation über keine Rechte verfügt, um sie als Hintergründe für Microsoft Teams-Besprechungen zu verwenden.

### <a name="allow-custom-background-settings"></a>Benutzerdefinierte Hintergrundeinstellungen zulassen

Sie können benutzerdefinierte Hintergrundbilder hinzufügen, die pro Mandant verwendet werden sollen. Mit diesem Feature können Unternehmen Unternehmensbranding auf Teams-Besprechungen anwenden.

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Wählen Sie **"Besprechungsrichtlinien** >  > **" aus, um Besprechungsbilder anzupassen**.

   ![Die Auswahl der Besprechungsrichtlinien mit hervorgehobener Schaltfläche "Besprechungsbilder anpassen".](media/custom-background-image-button.png)

3. Wählen Sie " **Ein** " aus **organisationsweiten Hintergrundbildern** aus.

4. Wählen Sie **Bilder aus, und fügen Sie sie hinzu**.

5. Wählen Sie im Bereich "Hintergründe verwalten" die Option " **Bild hinzufügen"** aus.

6. Stellen Sie sicher, dass die Bilder die folgenden Anforderungen erfüllen:
  
   - Mindestgröße 360 px
   - Maximale Größe 2048 px
   - Dateityp von PNG, JPG oder BMP
   - Maximal 50 Bilder können hochgeladen werden.

7. Zeigen Sie eine Vorschau der ausgewählten Bilder an, und wählen Sie dann **"Schließen**" aus.

8. Überprüfen Sie die Bilder, und fügen Sie nach Bedarf weitere hinzu.

9. Klicken Sie auf **Speichern**.

Den Besprechungsteilnehmern wird eine Auswahl von Hintergrundbildern angezeigt, die sie verwenden können, wenn sie an einer Besprechung teilnehmen.

> [!NOTE]
> Es kann bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.

> [!NOTE]
> Dieses Feature ist vorübergehend in der öffentlichen Vorschau für alle Microsoft Teams-Kunden verfügbar. Um dieses Feature nach der Vorschau zu erhalten, benötigt jeder Benutzer die Add-On-Lizenz "Erweiterte Kommunikation". Weitere Informationen finden Sie unter [Add-On für erweiterte Kommunikation für Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

### <a name="far-end-camera-control-fecc-for-point-tilt-zoom-ptz-cameras"></a>Far End Camera Control (FECC) für PTZ-Kameras (Point Tilt Zoom)

Die Fernend-Kamerasteuerung ist eine Richtlinie, die Teams-Räume auf Windows-Ressourcenkonten zugewiesen werden kann. Dadurch können PTZ-Kameras, die mit einem Teams-Raum verbunden sind, während Besprechungen von Besprechungsteilnehmern in der Teams-Client-App gesteuert werden.

Um die Fernkamerasteuerung zu verwenden, müssen Besprechungsteilnehmer die **PTZ-Kamerasteuerungs-App** abrufen.  Unter ["Apps zulassen und blockieren](manage-apps.md#allow-and-block-apps) " erfahren Sie, wie Sie die App im App Store Ihrer Organisation verfügbar machen.

Um anzugeben, wer die Kamerasteuerung am weitesten ende in einer Besprechung verwenden kann, erstellen und weisen Sie einem Teams-Räume Ressourcenkonto mithilfe des Cmdlets ["New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy?view=skype-ps)" eine neue Richtlinie zu, oder verwenden [Sie "Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)", um eine vorhandene zu ändern. Legen Sie den `TeamsCameraFarEndPTZMode` Parameter auf einen der folgenden Werte fest:

| Einstellungswert | Verhalten |
|---------------|----------|
|Deaktiviert | Dies ist die Standardeinstellung. Wenn sie auf "deaktiviert" festgelegt ist, kann niemand PTZ-Kamerasteuerelemente verwenden. |
|AutoAcceptAll | PTZ-Kamerasteuerelemente sind automatisch für jeden Besprechungsteilnehmer verfügbar. |
|AutoAcceptInTenant | PTZ-Kamerasteuerelemente sind automatisch nur für Teilnehmer in derselben Organisation wie der Teams-Raum verfügbar. |

Wenn `TeamsCameraFarEndPTZMode` diese Einstellung aktiviert `AutoAcceptAll` ist oder `AutoAcceptInTenant`kann die Kamerasteuerung jederzeit während einer Besprechung manuell aus dem Teams-Raum deaktiviert werden. Die Kamerasteuerung ist auch nicht verfügbar, wenn die Kamera ausgeschaltet ist.

Jede Kamera mit mechanischer PTZ- und UVC-Steuerung wird unterstützt. Eine Liste der für Teams zertifizierten Kameras, einschließlich PTZ- und Nicht-PTZ-Kameras, finden Sie unter ["Zertifizierte Firmwareversionen für USB-Audio- und Videoperipheriegeräte](rooms/requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)". Dieses Feature wird bei Kameras mit digitalen PTZ-Steuerelementen oder auf Teams-Räume unter Android noch nicht unterstützt.  

> [!NOTE]
> Aktualisieren Sie Ihre Kamerafirmware, bevor Sie PTZ-Steuerelemente testen. Informationen zum Aktualisieren der Firmware finden Sie in der Oem-Dokumentation (Original Equipment Manufacturer).

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)
