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
ms.openlocfilehash: 60891c2e5283b8e9cdaa9e8d7852768bbb52d8aa
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776930"
---
<a name="what-the-guest-experience-is-like"></a>Gastfunktionalität
=================================

Wenn ein Gast zu einem Team eingeladen wird, erhält er eine Willkommens-E-Mail-Nachricht. Diese Nachricht enthält einige Informationen zum Team und was ihn jetzt als Mitglied erwartet. Der Gast muss die Einladung in der E-Mail-Nachricht durch das Klicken auf **Microsoft Teams öffnen** annehmen, bevor er auf das Team und dessen Kanäle zugreifen kann.
    
![Screenshot mit einem Beispiel einer Willkommens-E-Mail](media/guest-experience-image1.png)
    
Alle Teammitglieder sehen eine Nachricht in einem Kanal-Thread. Darin werden die Mitglieder darüber informiert, dass der Teambesitzer einen Gast hinzugefügt hat, und der Name des Gasts wird angezeigt. Jeder im Team kann also sofort sehen, bei welchem Mitglied es sich um einen Gast handelt. Wie im folgenden Screenshot eines Beispielteams gezeigt, wird ein Banner mit dem Text „Dieses Team hat Gäste“ angezeigt, und neben jedem Gästenamen wird die Kennzeichnung **(Gast)** eingeblendet.
    
![Screenshot mit Banner-Benachrichtigung zu Gastbenutzern](media/guest-experience-image2.png "Screenshot, der einen Teil des Marketingkanals für Northwind Traders abbildet, auf dem Folgendes zu sehen ist: der Hinweis im oberen Banner, dass dieses Team Gäste hat, und das Wort „GAST“ neben dem Namen von Benutzern, die Gäste des Teams sind.")

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Vergleich der Funktionen für Team-Mitglieder und -Gäste

In der folgenden Tabelle werden die Microsoft Teams-Funktionen verglichen, die jeweils für die Mitglieder und die Gäste eines Teams einer Organisation verfügbar sind.

|**Funktionen in Teams**|**Teams-Benutzer in der Organisation**|**Gastbenutzer**|
|:-----|:-----|:-----|
|Erstellen eines Kanals  <br/>  *Diese Einstellung wird von Team-Besitzern gesteuert.*  <br/> |&#x2713;|&#x2713;|
|Teilnehmen an einem privaten Chat  <br/> |&#x2713;|&#x2713;|
|Teilnehmen an einer Kanalunterhaltung  <br/> |&#x2713;|&#x2713;|
|Posten, Löschen und Bearbeiten von Nachrichten  <br/> |&#x2713;|&#x2713;|
|Freigeben einer Kanal-Datei  <br/> |&#x2713;|&#x2713;|
|Freigeben einer Chatdatei  <br/> |&#x2713;||
|Hinzufügen von Apps (Registerkarten, Bots oder Connectors)  <br/> |&#x2713;||
|Erstellen von Besprechungen oder Zugreifen auf Zeitpläne  <br/> |&#x2713;||
|Zugreifen auf OneDrive for Business-Speicher  <br/> |&#x2713;||
|Erstellen von mandantenweiten Richtlinien und solchen für den Gastzugriff in Teams/Kanälen  <br/> |&#x2713;||
|Einladen eines Benutzers außerhalb der Domäne der Office 365-Organisation <br/>  *Teambesitzer steuern diese Einstellung.*  <br/> <br/> |&#x2713;||
|Erstellen eines Teams  <br/> |&#x2713;||
|Ein öffentliches Team suchen und daran teilnehmen  <br/> |&#x2713;||
|Einsicht nehmen in das Organigramm  <br/> |&#x2713;||
|Verwenden der Inline-Übersetzung  <br/> |&#x2713;||
|Teambesitzer werden  <br/> |&#x2713;||

   
In der folgenden Tabelle werden die für Gäste verfügbaren Anruf- und Besprechungsfeatures mit jenen für andere Benutzertypen verglichen.

| Anruffunktion | Gast | E1- und E3-Benutzer | E5- und Enterprise-VoIP-Benutzer |
| --------------- | ----- | -------------- | -------------- |
| VoIP-Anruf | Ja | Ja | Ja |
| Gruppenanrufe | Ja | Ja | Ja |
| Unterstützte zentrale Anruf-Steuerelemente (anhalten, Stummschaltung, Video ein/aus, Bildschirmfreigabe) | Ja | Ja | Ja |
| Durchstellungsziel | Ja | Ja | Ja |
| Können Anruf weiterleiten | Ja | Ja | Ja |
| Zu Gesprächsübergabe mit Ankündigung ermächtigt | Ja | Ja | Ja |
| Können weitere Benutzer zu einem Anruf über VoIP hinzufügen | Ja | Ja | Ja |
| Können Benutzer per Telefonnummer zu einem Anruf hinzufügen | Nein | Nein | Ja |
| Weiterleitungsziel | Nein | Ja | Ja |
| Anrufgruppenziel | Nein | Ja | Ja |
| Ziel für nicht beantwortet | Nein | Ja | Ja |
| Können Ziel für einen Verbundanruf sein | Nein | Ja | Ja |
| Können einen Verbundanruf tätigen | Nein | Ja | Ja |
| Können ihre Anrufe sofort weiterleiten | Nein | Nein | Ja |
| Können gleichzeitig Anrufe tätigen | Nein | Nein | Ja |
| Können ihre unbeantworteten Anrufe weiterleiten | Nein | Nein | Ja |
| Verpasste Anrufe können an Voicemail weitergeleitet werden | Nein | Nein<sup>1</sup> |Ja |
| Verfügt über eine Telefonnummer, mit der Anrufe empfangen werden können | Nein | Nein | Ja |
| Kann Telefonnummern anrufen | Nein | Nein | Ja |
| Hat Zugriff auf Anrufeinstellungen | Nein | Nein | Ja |
| Kann Voicemail-Begrüßung ändern | Nein | Nein<sup>1</sup> | Ja |
| Kann Klingeltöne ändern | Nein | Nein  | Ja |
| Unterstützt TTY | Nein | Nein | Ja |
| Können Stellvertretungen haben | Nein | Nein | Ja |
|  Können als Stellvertretung fungieren | Nein | Nein | Ja |


<sup>1</sup> Dieses Feature wird in Kürze verfügbar sein.

> [!NOTE]
> Office 365-Administratoren steuern die für Gäste verfügbaren Features. 

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="how-do-i-leave-an-organization-that-ive-been-invited-to"></a>Wie verlasse ich eine Organisation, zu der ich eingeladen wurde?
Wenn Sie zu einer Organisation eingeladen wurden, deren Gast Sie nicht sein möchten, können Sie diese verlassen. Weitere Informationen hierzu finden Sie unter [Verlassen einer Organisation als Gastbenutzer](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization). Alternativ können Sie den Administrator der Organisation bitten, Sie von seinem Mandanten zu entfernen. Beachten Sie, dass Sie in jedem Fall erneut zum Mandanten eingeladen werden müssen, wenn Sie zukünftig auf die Organisation zugreifen möchten.

### <a name="do-guests-have-the-same-capabilities-as-team-members"></a>Können Gäste auf die gleichen Funktionen wie Teammitglieder zugreifen?
Nein. Weitere Informationen dazu, was ein Gast tun kann und was nicht, finden Sie unter [Vergleich der Funktionen für Team-Mitglieder und -Gäste](#comparison-of-team-member-and-guest-capabilities) in diesem Artikel.

### <a name="do-guests-have-access-to-onedrive-for-business"></a>Haben Gäste Zugriff auf OneDrive for Business?
Nein.

### <a name="do-guests-have-access-to-sharepoint-files"></a>Haben Gäste Zugriff auf SharePoint-Dateien?
Ja.

### <a name="can-guests-search-within-files"></a>Können Gäste Suchen innerhalb von Dateien durchführen?
Nein.

### <a name="can-guests-attach-files"></a>Können Gäste Dateien anfügen?
Ja, ein Gast kann Dateien auf diese zwei Arten anfügen:

   - Indem er im linken Bereich **Dateien** auswählt und dann zum Dateispeicherort navigiert.
   - Indem er Dateien von seinem Computer hochlädt.

### <a name="can-a-guest-download-a-file-in-a-private-chat"></a>Kann ein Gast eine Datei in einen privaten Chat herunterladen?
Ja, ein Gast kann eine Datei von einem Mitglied in einem privaten Chat empfangen und dann auf seinen Desktop herunterladen.
