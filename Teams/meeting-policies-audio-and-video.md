---
title: Verwalten von Besprechungsrichtlinien für Audio und Video
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: 9cd2a82c87106e8060d168766915e4249b9193a5
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2021
ms.locfileid: "61177996"
---
# <a name="meeting-policy-settings-for-audio--video"></a>Besprechungsrichtlinieneinstellungen für & Video

<a name="bkaudioandvideo"> </a>
<a name="ndi"> </a>

In diesem Artikel werden die Besprechungsrichtlinieneinstellungen speziell für Audio und Video beschrieben. Diese beinhalten Folgendes:

- [Modus für IP-Audio](#mode-for-ip-audio)
- [Modus für IP-Video](#mode-for-ip-video)
- [IP-Video](#ip-video)
- [Media-Bitrate (KBs)](#media-bit-rate-kbs)
- [Videofiltermodus](#video-filters-mode)
- [Benutzerdefinierte Hintergrundeinstellungen zulassen](#allow-custom-background-settings)

### <a name="mode-for-ip-audio"></a>Modus für IP-Audio

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Audio in Besprechungen und Gruppenanrufen aktiviert werden kann. Nachfolgend sind die Werte für diese Einstellung aufgeführt.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Ausgehendes und eingehendes Audio aktiviert**    |Ausgehendes und eingehendes Audio ist in der Besprechung zulässig. Dies ist die Standardeinstellung. |
|**Deaktiviert**     |Ausgehendes und eingehendes Audio ist in der Besprechung deaktiviert.     |

Wenn für einen Benutzer **Deaktiviert** festgelegt ist, kann er weiterhin Besprechungen planen und organisieren, jedoch kein Audio verwenden. Wenn er an einer Besprechung teilnehmen möchte, muss er sich über das öffentliche Festnetz einwählen, oder sich aus der Besprechung anrufen lassen und per Telefon daran teilnehmen. Für Besprechungsteilnehmer, denen keine Richtlinien zugewiesen sind (z. B. anonyme Teilnehmer), ist diese Einstellung standardmäßig auf **Ausgehendes und eingehendes Audio aktiviert** festgelegt. Wenn diese Einstellung auf mobilen Microsoft Teams-Clients deaktiviert ist, muss sich der Benutzer über das öffentliche Telefonnetz einwählen, um an einer Besprechung teilzunehmen.

Diese Einstellung gilt nicht für Einzelanrufe. Wenn Sie Einzelanrufe einschränken möchten, konfigurieren Sie eine Microsoft Teams-[Anrufrichtlinie](teams-calling-policy.md), und deaktivieren Sie die Einstellung für das Tätigen **privater Anrufe**. Diese Einstellung gilt auch nicht für Konferenzraumgeräte wie Surface Hub und Geräte für Microsoft Teams-Räume.

Diese Einstellung ist noch nicht für die Microsoft 365 Government Community Cloud (GCC), GCC High- und DoD-Umgebungen (Department of Defense) verfügbar.

Weitere Informationen hierzu finden Sie unter [Audio/Video für Besprechungsteilnehmer verwalten](#manage-audiovideo-for-meeting-participants).

### <a name="mode-for-ip-video"></a>Modus für IP-Video

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Video in Besprechungen und Gruppenanrufen aktiviert werden kann. Nachfolgend sind die Werte für diese Einstellung aufgeführt.

|Einstellungswert |Verhalten  |
|---------|---------|
|**Ausgehendes und eingehendes Video aktiviert**    | Ausgehendes und eingehendes Video ist in der Besprechung zulässig. Dies ist die Standardeinstellung. |
|**Deaktiviert**     | Ausgehendes und eingehendes Video ist in der Besprechung deaktiviert. Auf mobilen Microsoft Teams-Clients können Benutzer keine Videos oder Fotos in der Besprechung freigeben. <br><br>Beachten Sie: Wenn der **Modus für IP-Audio** deaktiviert ist, bleibt auch der **Modus für IP-Video** deaktiviert.  |

Wenn diese Einstellung für einen Benutzer **deaktiviert** ist, kann dieser die Videofunktion nicht aktivieren und auch keine Videos anzeigen, die von anderen Besprechungsteilnehmern geteilt werden. Für Besprechungsteilnehmer, denen keine Richtlinien zugewiesen sind (z. B. anonyme Teilnehmer), ist diese Einstellung standardmäßig auf **Ausgehendes und eingehendes Video aktiviert** festgelegt.

Diese Einstellung gilt nicht für Konferenzraumgeräte wie Surface Hub und Geräte für Microsoft Teams-Räume.

Diese Einstellung ist noch nicht für die Microsoft 365 Government Community Cloud (GCC), GCC High- und DoD-Umgebungen (Department of Defense) verfügbar.

> [!NOTE]
> Beachten Sie, dass diese Einstellung sowohl das ausgehende als auch das eingehende Video steuert, während die **IP-Videoeinstellung** ausgehendes Video steuert. Weitere Informationen hierzu finden Sie unter [Welche IP-Videorichtlinieneinstellung hat Vorrang?](#which-ip-video-policy-setting-takes-precedence) und [Audio/Video für Besprechungsteilnehmer verwalten](#manage-audiovideo-for-meeting-participants).

Weitere Informationen hierzu finden Sie unter [Audio/Video für Besprechungsteilnehmer verwalten](#manage-audiovideo-for-meeting-participants).

### <a name="ip-video"></a>IP-Video

Hierbei handelt es sich um eine Kombination aus einer benutzerspezifischen und einer organisatorspezifischen Richtlinie. Die Videofunktion ist ein Schlüsselelement in Besprechungen. In einigen Organisationen möchten Administratoren möglicherweise mehr Kontrolle darüber haben, in welchen Besprechungen der Benutzer Video genutzt werden kann. Über diese Einstellung wird gesteuert, ob Video in von einem Benutzer gehosteten Besprechungen oder in von einem Benutzer gestarteten Einzel- und Gruppenanrufen eingeschaltet werden kann. Auf Teams mobilen Clients steuert diese Einstellung, ob Benutzer Fotos und Videos in einer Besprechung teilen können.

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

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>Welche Einstellung der IP-Videorichtlinie hat Vorrang?

Für einen Benutzer hat die restriktivste Richtlinieneinstellung für Videos Vorrang. Hier sind einige Beispiele.

|IP-Video|Modus für IP-Video|Auswirkung|
|---------|---------|---------|
|Organisator: **Aktiviert**<br><br>Teilnehmer: **Aktiviert** |Teilnehmer: **Deaktiviert**        |Die Einstellung für den **Modus für IP-Video** hat Vorrang. Ein Teilnehmer, dem diese Richtlinie zugewiesen ist, kann die von anderen Personen freigegebenen Videos weder aktivieren noch anzeigen.|
|Organisator: **Aktiviert**<br><br>Teilnehmer: **Aktiviert** |Teilnehmer: **Ausgehendes und eingehendes Video aktiviert**          |Ein Teilnehmer, dem diese Richtlinie zugewiesen ist, kann von anderen Personen freigegebene Videos aktivieren und anzeigen.         |
|Organisator: **Aktiviert**<br><br>Teilnehmer: **Deaktiviert** |Teilnehmer: **Ausgehendes und eingehendes Video aktiviert**         |Die **Einstellung IP-Video** hat Vorrang. Die Teilnehmer können nur eingehende Videos anzeigen und keine ausgehenden Videos senden.         |
|Organisator: **Aktiviert**<br><br>Teilnehmer: **Deaktiviert** |Teilnehmer: **Deaktiviert**         |Die Einstellung für den **Modus für IP-Video** hat Vorrang. Der Teilnehmer kann weder eingehende noch ausgehende Videos anzeigen.|
|Organisator: **Deaktiviert**    |       |Die **Einstellung IP-Video** hat Vorrang, da sie für den Organisator deaktiviert ist. Niemand kann die Videofunktion in Besprechungen aktivieren, die von dem Benutzer organisiert wurden, dem diese Richtlinie zugewiesen wurde.         |

### <a name="manage-audiovideo-for-meeting-participants"></a>Audio/Video für Besprechungsteilnehmer verwalten

|Sie möchten ...  |Legen Sie die folgenden Richtlinieneinstellungen fest  |
|---------|---------|
|Audio und Video für Teilnehmer in Besprechungen deaktivieren  |Modus für IP-Audio: **Deaktiviert**<br> Modus für IP-Video: **Deaktiviert**<br>IP-Video: N/A       |
|Nur eingehendes Video und Audio für Teilnehmer in Besprechungen aktivieren  |Modus für IP-Audio: **Ausgehendes und eingehendes Audio aktiviert**<br> Modus für IP-Video: **Ausgehendes und eingehendes Video aktiviert**<br>IP-Video: **Aus**       |
|Video für Teilnehmer in Besprechungen deaktivieren (für die Teilnehmer ist nur Audio verfügbar)|  Modus für IP-Audio: **Ausgehendes und eingehendes Audio aktivieren**<br> Modus für IP-Video: **Deaktiviert**<br>IP-Video: N/A
|Audio und Video für Teilnehmer in Besprechungen aktivieren    |Modus für IP-Audio: **Ausgehendes und eingehendes Audio aktiviert** (Standard)<br> Modus für IP-Video: **Ausgehendes und eingehendes Video aktiviert** (Standard)<br>IP-Video: **Ein** (Standard)    |

Die restriktivste Richtlinie zwischen der Richtlinie des Besprechungsorganisators und jener des Benutzers hat Vorrang. Wenn für den Organisator beispielsweise eine Richtlinie gilt, die Video einschränkt, und die für den Benutzer geltende Richtlinie Video nicht einschränkt, erben Besprechungsteilnehmer die Richtlinie des Besprechungsorganisators und haben in Besprechungen keinen Zugriff auf die Videofunktion. Dies bedeutet, dass sie an der Besprechung nur per Audio teilnehmen können.

> [!NOTE]
> Wenn ein Benutzer einen Gruppenanruf startet, bei dem man über das Telefon teilnimmt, wird der Bildschirm **Telefon für Audio verwenden** nicht angezeigt. Dieses Problem ist bekannt, und wir arbeiten an einer Lösung. Um dieses Problem zu umgehen, wählen Sie **Telefon-Audio** unter **Andere Verbindungsoptionen** aus.  

#### <a name="teams-mobile-clients"></a>Mobile Microsoft Teams-Clients

Für Benutzer auf Teams mobilen Clients wird die Möglichkeit zur Freigabe von Fotos und Videos während einer Besprechung auch durch die **Einstellung für den IP-Video-** oder **IP-Videomodus** bestimmt. Je nachdem, welche Richtlinieneinstellung Vorrang hat, ist die Option zum Teilen von Videos und Fotos nicht verfügbar. Dies wirkt sich nicht auf die Bildschirmfreigabe aus, die diese über eine eigene Einstellung für den [Bildschirmfreigabemodus](meeting-policies-content-sharing.md#screen-sharing-mode) konfiguriert wird. Darüber hinaus können Sie eine [Microsoft Teams-Richtlinie für Mobilgeräte](/powershell/module/skype/new-csteamsmobilitypolicy) festlegen, um zu verhindern, dass Benutzer von Mobilgeräten die IP-Videofunktion über eine Mobilverbindung verwenden; dies bedeutet, dass sie eine WLAN-Verbindung verwenden müssen.

### <a name="media-bit-rate-kbs"></a>Media-Bitrate (KBs)

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Diese Einstellung bestimmt für den Benutzer die Medienbitrate für Audio-, Video- und videobasierte App-Übertragung bei Anrufen und in Besprechungen. Sie wird sowohl auf die Uplink- als auch auf die Downlink-Medienübertragung für die Benutzer die sich in einem Anruf oder einer Besprechung befinden, angewendet. Mit dieser Einstellung können Sie die Bandbreite in Ihrer Organisation präzise kontrollieren und verwalten. Je nach Szenario, das die Benutzer benötigen, empfiehlt es sich, genügend Bandbreite für eine bereitzustellen, um eine gute, qualitativ hochwertige Erfahrung zu gewährleisten. Der Mindestwert beträgt 30 KBit/s. Der Höchstwert ist von der jeweiligen Besprechungssituation abhängig. Weitere Informationen zur empfohlenen Mindestbandbreite für Besprechungen, Anrufe und Live-Ereignisse in hoher Qualität in Microsoft Teams finden Sie unter [Bandbreitenanforderungen](prepare-network.md#bandwidth-requirements).

Wenn für eine Besprechung nicht genügend Bandbreite verfügbar ist, wird den Teilnehmern eine Nachricht angezeigt, die auf die geringe Übertragungsleistung hinweist.

Wenn Sie Besprechungen mit höchster Videoqualität, z. B. Vorstandssitzungen oder Microsoft Teams-Liveereignisse, organisieren wollen, empfehlen wir, die Bandbreite auf 10 Mbit/s festzulegen. Selbst wenn die Einstellungen für ein möglichst hochwertiges Ergebnis festgelegt wurden, passt sich der Microsoft Teams-Medienstack an die Bedingungen geringer Bandbreite an, wenn abhängig vom Szenario bestimmte Netzwerkbedingungen ermittelt wurden.

## <a name="video-filters-mode"></a>Videofiltermodus

<a name="bkvideofilters"> </a>

Hierbei handelt es sich um eine benutzerspezifische Richtlinie. Über diese Einstellung wird gesteuert, ob Benutzer ihre Videohintergründe in einer Besprechung anpassen können.

Sie können diese Richtlinie Teams Admin Center und PowerShell festlegen. Sie können eine vorhandene Microsoft Teams-Besprechungsrichtlinie mithilfe des Cmdlets [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) bearbeiten. Sie können aber auch eine neue Besprechungsrichtlinie für Microsoft Teams mithilfe des Cmdlets [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) erstellen und sie dann Benutzern zuweisen.

Um anzugeben, ob Benutzer ihren Videohintergrund in einer Besprechung anpassen können, legen Sie den **Parameter VideoFiltersMode** **(Einstellung** Videofilter im Teams Admin Center auswählen) wie folgt fest:

|Festzulegender Wert in PowerShell|Festlegen eines Werts im Teams Admin Center |Verhalten  |
|---------|---------|---------|
|**NoFilters** |**Kein Filter**    |Der Benutzer kann seinen Videohintergrund nicht anpassen.|
|**BlurOnly**     |**Nur Weichr für den Hintergrund**|Der Benutzer hat die Möglichkeit, den Hintergrund des Videos weichzuzeichnen. |
|**BlurandDefaultBackgrounds**|**Weich weicher Hintergrund und Standardbilder**     |Der Benutzer hat die Möglichkeit, den Hintergrund des Videos weichzuzeichnen oder eines der Standardbilder auszuwählen, die als Hintergrund verwendet werden können. |
|**AllFilters**|**Alle Filter**     |Der Benutzer hat die Möglichkeit, den Hintergrund des Videos weichzuzeichnen, eines der Standardbilder auszuwählen oder ein eigenes Bild hochzuladen, um es als Hintergrund zu verwenden. |

> [!NOTE]
> Bilder, die von Benutzern hochgeladen wurden, werden von Microsoft Teams nicht überprüft. Wenn Sie die Einstellung **AllFilters** verwenden, sollten Sie über interne Richtlinien für Ihre Organisation verfügen, um zu verhindern, dass Benutzer anstößige oder unangemessene Bilder hochladen oder solche, für die Ihre Organisation über keine Rechte verfügt, um sie als Hintergründe für Microsoft Teams-Besprechungen zu verwenden.

### <a name="allow-custom-background-settings"></a>Benutzerdefinierte Hintergrundeinstellungen zulassen

Sie können benutzerdefinierte Hintergrundbilder hinzufügen, die pro Mandant verwendet werden sollen. Dieses Feature ermöglicht Unternehmen das Anwenden von Unternehmensbranding auf Teams Besprechungen.

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Wählen Sie   >  **Besprechungsrichtlinien Besprechungsrichtlinien**  >  **Anpassen von Besprechungsbildern aus.**

   ![Auswahl der Besprechungsrichtlinien mit hervorgehobener Schaltfläche "Besprechungsbilder anpassen".](media/custom-background-image-button.png)

3. Wählen Sie **in Organisationsweite** **Hintergrundbilder die Option Ein aus.**

4. Wählen Sie **+ Bilder hinzufügen aus.**

5. Wählen Sie im Bereich Hintergründe verwalten die Option **Bild hinzufügen aus.**

6. Stellen Sie sicher, dass die Bilder die folgenden Anforderungen erfüllen:
  
   - Mindestgröße 360 px
   - Maximale Größe 2048 px
   - Dateityp PNG, JPG oder BMP
   - Maximal 50 Bilder können hochgeladen werden

7. Zeigen Sie eine Vorschau der ausgewählten Bilder an, und wählen Sie dann **Schließen aus.**

8. Überprüfen Sie die Bilder, und fügen Sie nach Bedarf weitere hinzu.

9. Klicken Sie auf **Speichern**.

Die Besprechungsteilnehmer sehen eine Auswahl von Hintergrundbildern, die sie für die Teilnahme an einer Besprechung verwenden können.

> [!NOTE]
> Es kann bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Benutzern in Microsoft Teams Richtlinien zuweisen](policy-assignment-overview.md)
