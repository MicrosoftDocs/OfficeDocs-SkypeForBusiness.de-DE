---
title: Gastfunktionalität
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Hier erhalten Sie Informationen zu der für Gastbenutzer verfügbaren Microsoft Teams-Funktionalität.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed0ea94910e9b3b5499a1f23a6c1c081590957c7
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160569"
---
<a name="what-the-guest-experience-is-like"></a>Gastfunktionalität
=================================

Wenn ein Gast zur Teilnahme an einem Team eingeladen wird, erhält er eine Willkommens-e-Mail-Nachricht. Diese Nachricht enthält einige Informationen über das Team und was Sie jetzt erwarten können, wenn Sie Mitglied sind. Der Gast muss die Einladung akzeptieren, indem er in der e-Mail-Nachricht **Microsoft Teams öffnen** auswählt, bevor er auf das Team und seine Kanäle zugreifen kann.
    
![Screenshot mit einem Beispiel einer Willkommens-e-Mail-Nachricht](media/guest-experience-image1.png)
    
Alle Teammitglieder sehen eine Nachricht in einem Kanal-Thread. Darin werden die Mitglieder darüber informiert, dass der Teambesitzer einen Gast hinzugefügt hat, und der Name des Gasts wird angezeigt. Jeder im Team kann also sofort sehen, bei welchem Mitglied es sich um einen Gast handelt. Wie im folgenden Screenshot eines Beispiel Teams zu sehen ist, wird in einem Banner "dieses Team hat Gäste" angezeigt, und neben dem Namen jedes Gasts wird eine **(Gast-)** Beschriftung angezeigt.
    
![Screenshot mit Banner Benachrichtigungs Gastbenutzern](media/guest-experience-image2.png "Screenshot zeigt einen Teil des Marketing Kanals für Northwind Traders, wobei die Benachrichtigung im oberen Banner besagt, dass das Team Gäste und Benutzer hat, die Gäste sind, die mit dem Wort Guest neben dem Namen der Person gekennzeichnet sind.")

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Vergleich von Teammitgliedern und Gast Funktionen

In der folgenden Tabelle werden die für die Teammitglieder und ihre Gäste des Unternehmens verfügbaren Funktionen für Teams verglichen.

|**Funktionen in Teams**|**Teams-Benutzer in der Organisation**|**Gastbenutzer**|
|:-----|:-----|:-----|
|Kanal erstellen  <br/>  *Teambesitzer steuern diese Einstellung.*  <br/> |&#x2713;|&#x2713;|
|An einem privaten Chat teilnehmen  <br/> |&#x2713;|&#x2713;|
|An einer Kanalunterhaltung teilnehmen  <br/> |&#x2713;|&#x2713;|
|Nachrichten posten, löschen und bearbeiten  <br/> |&#x2713;|&#x2713;|
|Kanaldatei freigeben  <br/> |&#x2713;|&#x2713;|
|Chatdatei freigeben  <br/> |&#x2713;||
|Apps hinzufügen (Registerkarten, Bots oder Connectors)  <br/> |&#x2713;||
|Erstellen von Besprechungen oder Zugriffsplänen  <br/> |&#x2713;||
|Access OneDrive for Business-Speicher  <br/> |&#x2713;||
|Mandantenweite Gastzugriffsrichtlinien für Teams/Kanäle erstellen  <br/> |&#x2713;||
|Benutzer außerhalb der Office 365-Mandantendomäne einladen <br/>  *Teambesitzer steuern diese Einstellung.*  <br/> <br/> |&#x2713;||
|Team erstellen  <br/> |&#x2713;||
|Öffentliches Team finden und daran teilnehmen  <br/> |&#x2713;||
|Organisationschat anzeigen  <br/> |&#x2713;||
|Verwenden der Inline Übersetzung  <br/> |&#x2713;||
|Teambesitzer werden  <br/> |&#x2713;||

   
In der folgenden Tabelle sind die für Gäste verfügbaren Anruf-und besprechungsfeatures im Vergleich zu anderen Benutzertypen aufgeführt.

| Anruffunktion | Gäste | E1-und E3-Benutzer | E5 und Enterprise-VoIP-Benutzer |
| --------------- | ----- | -------------- | -------------- |
| VoIP-Anrufe | Ja | Ja  | Ja  |
| Gruppenanrufe | Ja | Ja  | Ja  |
| Unterstützte zentrale Anrufsteuerungen (halten, stumm schalten, Video ein/aus, Bildschirmübertragung) | Ja | Ja  | Ja  |
| Übergabeziel | Ja | Ja  | Ja  |
| Kann einen Anruf übertragen | Ja | Ja  | Ja  |
| Kann beratend übertragen | Ja | Ja  | Ja  |
| Kann andere Benutzer zu einem Anruf über VoIP hinzufügen | Ja | Ja  | Ja  |
| Kann Nutzer per Telefonnummer zu einem Anruf hinzufügen | Nein | Nein | Ja |
| Ziel weiterleiten | Nein | Ja | Ja  |
| Anrufgruppen Ziel | Nein | Ja | Ja  |
| Unbeantwortetes Ziel | Nein | Ja | Ja  |
| Kann das Ziel eines Föderations Anrufs sein | Nein | Ja | Ja  |
| Kann einen Verbund Anruf führen | Nein | Ja | Ja  |
| Kann Ihre Anrufe sofort weiterleiten | Nein | Nein | Ja |
| Können gleichzeitig anrufen | Nein | Nein | Ja |
| Kann Ihre unbeantworteten Anrufe weiterleiten | Nein | Nein | Ja |
| Verpasste Anrufe können an Voicemail weitergeleitet werden | Nein | Nr.<sup>1</sup> |Ja |
| Haben Sie eine Telefonnummer, mit der Sie Anrufe empfangen können | Nein | Nein | Ja |
| Kann Telefonnummern anrufen | Nein | Nein | Ja |
| Kann auf Anrufeinstellungen zugreifen | Nein | Nein | Ja |
| Kann Voicemail-Ansage ändern | Nein | Nr.<sup>1</sup> | Ja |
| Kann Klingeltöne ändern | Nein | Nein  | Ja |
| Unterstützt TTY | Nein | Nein | Ja |
| Kann Stellvertretungen haben | Nein | Nein | Ja |
|  Kann eine Stellvertretung sein | Nein | Nein | Ja |


<sup>1</sup> dieses Feature wird in Kürze zur Verfügung stehen.

> [!NOTE]
> Office 365-Administratoren steuern die für Gäste verfügbaren Funktionen. 

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="how-do-i-leave-an-organization-that-ive-been-invited-to"></a>Wie verlasse ich eine Organisation, zu der ich eingeladen wurde?
Wenn Sie zu einer Organisation eingeladen wurden, in der Sie nicht Gast sein möchten, können Sie die Organisation belassen. Weitere Informationen finden Sie unter [verlassen einer Organisation als Gastbenutzer](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization). Alternativ können Sie den Administrator der Organisation bitten, Sie von Ihrem Mandanten zu entfernen. Beachten Sie, dass Sie in beiden Fällen erneut zu dem Mandanten eingeladen werden müssen, wenn Sie zukünftig auf die Organisation zugreifen möchten.

### <a name="do-guests-have-the-same-capabilities-as-team-members"></a>Haben Gäste die gleichen Fähigkeiten wie Teammitglieder?
Nummer Weitere Informationen dazu, was ein Gast tun kann und was nicht, finden Sie unter [Vergleich von Teammitgliedern und Gast Funktionen](#comparison-of-team-member-and-guest-capabilities) in diesem Artikel.

### <a name="do-guests-have-access-to-onedrive-for-business"></a>Haben Gästezugriff auf OneDrive for Business?
Nummer

### <a name="do-guests-have-access-to-sharepoint-files"></a>Haben Gästezugriff auf SharePoint-Dateien?
Ja.

### <a name="can-guests-search-within-files"></a>Können Gäste in Dateien suchen?
Nummer

### <a name="can-guests-attach-files"></a>Können Gäste Dateien anfügen?
Ja, ein Gast kann Dateien auf diese zwei Arten anfügen:

   - Wählen Sie im linken Bereich **Dateien** aus, und navigieren Sie dann zum Dateispeicherort.
   - Laden Sie Dateien von Ihrem Computer hoch.

### <a name="can-a-guest-download-a-file-in-a-private-chat"></a>Kann ein Gast eine Datei in einem privaten Chat herunterladen?
Ja, Sie können eine Datei von einem Mitglied in einem privaten Chat empfangen und dann auf Ihren Desktop herunterladen.
