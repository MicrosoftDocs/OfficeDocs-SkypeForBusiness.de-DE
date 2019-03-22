---
title: Bekannte Probleme für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 2/25/2019
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: marcl
localization_priority: Priority
search.appverid: MET150
description: Aktuelle Liste der bekannten Probleme für die Microsoft Teams-Client-App und Administratorfunktionen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2908ff9bec8be1eaf7d6dc09ff03adb9ae3ea9ea
ms.sourcegitcommit: cad74f2546a6384747b1280c3d9244aa13fd0989
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737816"
---
# <a name="known-issues-for-microsoft-teams"></a>Bekannte Probleme für Microsoft Teams

Dieser Artikel listet die bekannten Probleme für Microsoft Teams nach Funktionsbereichen auf.

## <a name="administration"></a>Verwaltung

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Überwachungsprotokolle melden möglicherweise einen falschen Benutzernamen als Initiator, wenn jemand aus einem Team entfernt wurde.  <br/> |Ein Team aus Microsoft Teams entspricht in AAD einer modernen Gruppe. Wenn Sie über die Microsoft Teams-Benutzeroberfläche ein Mitglied hinzufügen bzw. entfernen, ist genau bekannt, welcher Benutzer die Änderung initiiert hat, und das Überwachungsprotokoll gibt die richtigen Informationen wieder. Wenn jedoch ein Benutzer über AAD ein Mitglied entfernt oder hinzufügt, wird die Änderung mit dem Microsoft Teams-Back-End synchronisiert, ohne dass Microsoft Teams erfährt, wer die Aktion initiiert hat. Microsoft Teams sucht den ersten Besitzer des Teams als Initiator aus. Dies geht letztendlich auch aus dem Überwachungsprotokoll hervor.    <br/> |  <br/> |11.05.2018  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Die EAF-Richtlinie im Enhanced Mitigation Experience Toolkit (EMET) identifiziert möglicherweise Chromium-Sandkastenoptimierungen fälschlich als Bedrohungen. <br/> |Im Zusammenhang mit Chromium-Sandkästen besteht ein Problem, bei dem die EAF-Richtlinie (Export Address Table Access Filtering) im Enhanced Mitigation Experience Toolkit (EMET) und in Windows Defender Advanced Threat Protection (ATP) Chromium-Sandkastenoptimierungen möglicherweise fälschlich als Bedrohungen identifiziert. Dies führt dazu, dass Microsoft Teams nicht ordnungsgemäß funktioniert.  <br/> | Deaktivieren Sie EAF für Microsoft Teams, um das Problem zu umgehen. Unter [Richtlinien zu EMET-Sicherheitstechnologien zur Schadensbegrenzung](https://support.microsoft.com/de-DE/help/2909257/emet-mitigations-guidelines) können Sie mehr über dieses Problem lesen. Weitere Informationen zu Windows Defender ATP und zur EAF-Richtlinie finden Sie unter [Anpassen des Exploit-Schutzes](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/customize-exploit-protection). <br/> |11.10.2018 <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Wenn „UsersPermissionToReadOtherUsersEnabled“ auf „False“ festgelegt ist, können keine Mitglieder zu Teams hinzugefügt werden.  <br/> |Wenn dieser Wert in AAD auf „False“ festgelegt ist, können Sie in Microsoft Teams keine externen bzw. internen Mitglieder hinzufügen. Außerdem wird die folgende Fehlermeldung angezeigt: „Mitglied konnte nicht hinzugefügt werden. Es ist ein Problem aufgetreten. Bitte versuchen Sie es später erneut.“ Mitglieder können jedoch direkt zu Office 365-Gruppen hinzugefügt werden.    <br/> |Ändern Sie diese Einstellung in AAD in „True“.  <br/> |10.04.18  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Die Administratorverwaltung für mandantenweite Connectors ist nicht mehr verfügbar.  <br/> |Beim Versuch, einen Connector hinzuzufügen, wird in der Clientversion und in der Onlineversion die folgende Fehlermeldung angezeigt: „An unexpected error occurred. Please try again.“ (Unerwarteter Fehler. Versuchen Sie es erneut.). „Set-OrganizationConfig -ConnectorsEnabled=True“   <br/> |Verwenden Sie zum Deaktivieren die Microsoft Teams-Einstellungen. Lesen Sie diesen Supportartikel: https://answers.microsoft.com/en-us/msoffice/forum/msoffice_o365admin-mso_teams-mso_o365b/how-to-enable-or-disable-connectors-in-office-365/33d4b2c1-00eb-420a-ad83-01a2b42ad098    <br/> |21.06.17  <br/> |

## <a name="apps"></a>Apps

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|[Bedingter Zugriff](https://docs.microsoft.com/de-DE/azure/active-directory/conditional-access/overview) funktioniert möglicherweise nicht, wenn Sie die Registerkarte "Website" in der Desktop-App verwenden.<br/> |Wenn eine Website, wie z. B. ein Intranetportal, über Richtlinien für bedingten Zugriff verfügt (etwa Browser- oder IP-Adressbeschränkungen), kann es sein, dass diese Website in der Desktop-App nicht als Registerkarte innerhalb von Teams angezeigt wird. <br/> |Verwenden Sie anstatt der Desktop-App Teams in einem Browser.  <br/> |1.7.18  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Für einige Teams fehlen die Connector-Optionen.  <br/> |Wenn Sie mit der rechten Maustaste auf einen Kanal klicken, ist die Option für Connectors für keines der Teammitglieder vorhanden.  <br/> |Der Ersteller des Teams benötigt ein Onlinepostfach, andernfalls ist keine Connector-Option verfügbar. Dieses Verhalten ist zu erwarten.  <br/> |26.06.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Die App „Aufgaben“ bleibt sichtbar, obwohl sie deaktiviert wurde.  <br/> |Wenn die App „Aufgaben“ im Admin Center deaktiviert wird, bleibt sie für Benutzer mit EDU-Lizenz im Microsoft Teams-Client sichtbar. Wenn die deaktivierte App ausgewählt wird, wird die folgende Fehlermeldung zurückgegeben: „Leider ist etwas schiefgegangen ...“.  <br/> |Keine Problemumgehung.  <br/> |29.12.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Es ist nicht möglich, als Teambesitzer Connectors zu löschen.  <br/> |Beim Versuch, als Besitzer, der sonst Connectors hinzufügen kann, einen Connector zu löschen, während „Zulassen, dass Mitglieder Connectors erstellen, aktualisieren und entfernen“ deaktiviert ist, wird eine Fehlermeldung ausgelöst. Aus dieser geht hervor, dass der Benutzer nicht über die entsprechende Berechtigung verfügt. <br/> |Wenn „Zulassen, dass Mitglieder Connectors erstellen, aktualisieren und entfernen“ vorübergehend aktiviert wird, kann der Besitzer den Connector löschen.  <br/> |27.07.2018  <br/> |

## <a name="audio-conferencing"></a>Audiokonferenzen

|**Problem**|**Verhalten/Symptome**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|PSTN-Anrufer mit der gleichen „Von"-Nummer werden in der Teilnehmerliste der Besprechung als derselbe Benutzer angezeigt.  <br/> |Wenn mehrere PSTN-Anrufer an einer Besprechung teilnehmen und ihre Anrufer-IDs als eine einzige Nummer gekennzeichnet sind, werden diese Anrufer in der Teilnehmerliste der Besprechung als ein einziger Anrufer angezeigt.  <br/> |Keine Problemumgehung.  <br/> |25.09.2017  <br/> |
|Der Bereich mit den Besprechungsinformationen wird zeitweise nicht angezeigt.  <br/> |Der Bereich mit den Besprechungsinformationen wird im Teams-Client möglicherweise nicht angezeigt, wenn Benutzer versuchen, Telefonnummern einer Konferenzbrücke oder Konferenzkennungen nachzuschlagen.  <br/> |Sie können die Telefonnummern einer Konferenzbrücke oder Konferenzkennungen in den Besprechungsdetails oder im Outlook-Kalender anzeigen.  <br/> |25.09.2017  <br/> |
|Besprechungseinladungen über das Outlook-Add-In enthalten sinnlose Zeichen in PSTN-Koordinaten für Nicht-US-Gebietsschemas.  <br/> |Beim Planen von privaten Besprechungen mit dem Outlook-Add-In für Microsoft Teams auf einem Computer mit Nicht-US-Gebietsschemas enthalten PSTN-Koordinaten möglicherweise sinnlose Zeichen.  <br/> |Keine Problemumgehung.  <br/> |25.09.2017  <br/> |
|Bei der Auswahl müssen mindestens fünf Ziffern verwendet werden.  <br/> |Benutzer, die aus einer Besprechung eine Nummer zu wählen versuchen, müssen mindestens fünf Ziffern eingeben, obwohl eine Wählplan-Normalisierungsregel verfügbar ist, durch die gewählte kurze Nummern in E.164 normalisiert werden.  <br/> |Geben Sie bei der Auswahl anstelle der internen Durchwahlnummer die Nummer im vollständigen Durchwahlnummernformat oder lokalen Nummernformat ein.  <br/> |25.09.2017  <br/> |
|Das Auswahlsteuerelement wird zeitweise nicht angezeigt.  <br/> |Das Auswahlsteuerelement ist möglicherweise im Bereich mit den Besprechungsinformationen nicht sichtbar.  <br/> |Keine Problemumgehung.  <br/> |25.09.2017  <br/> |
|Statische Konferenzkennungen werden für Microsoft Teams-Besprechungen nicht unterstützt.  <br/> |Wenn der Administrator die Standardeinstellung außer Kraft setzt und sie von einer dynamischen Konferenzkennung in eine statische Konferenzkennung ändert, wird diese Einstellung für Microsoft Teams-Besprechungen nicht wirksam. Siehe [Verwenden von dynamischen IDs für Audiokonferenzen in Ihrer Organisation](/skypeforbusiness/audio-conferencing-in-office-365/using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Keine Problemumgehung.  <br/> |25.09.2017  <br/> |
|PSTN-Besprechungs-Koordinaten sind nicht verfügbar für lokale Benutzer von Skype for Business  <br/> |Wenn es sich bei dem Benutzer um einen lokalen Skype Business-Benutzer handelt, der mit Lizenzen für Skype for Business Online, Audiokonferenzen und Teams ausgestattet ist, enthalten alle Meetings, die mit Teams geplant sind, keine PSTN-Meeting-Koordinaten. <br/> |Keine Problemumgehung.  <br/> |01.02.2018  <br/> |

## <a name="authentication"></a>Authentifizierung

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Wenn Sie Microsoft Teams über Internet Explorer oder Microsoft Edge beitreten, entsteht im Programm eine Dauerschleife, oder das Programm stürzt ab, und die Anmeldung funktioniert nicht.   <br/> | Ihre Organisation nutzt die Option „Vertrauenswürdige Sites“ in Internet Explorer, und die Anmeldung über die webbasierte Microsoft Teams-Anwendung funktioniert nicht richtig, da vertrauenswürdige Sites für Microsoft Teams nicht zulässig sind. <br/>|Nehmen Sie mit Administratorrechten oder über ein Gruppenrichtlinienobjekt die folgenden Änderungen an den Internet Explorer-Einstellungen oder in der Systemsteuerung vor:<br/><ol><li>Akzeptieren Sie unter **Internetoptionen** &gt; **Datenschutz** &gt; **Erweitert** Cookies von Erstanbietern und Cookies von Drittanbietern, und aktivieren Sie das Kontrollkästchen **Sitzungscookies immer zulassen**.</li><li>Klicken Sie auf **Internetoptionen** &gt; **Sicherheit** &gt; **Vertrauenswürdige Sites** &gt; **Sites**, und fügen Sie alle folgenden Sites hinzu:<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>HINWEIS</b>: Validieren Sie immer alle vertrauenswürdigen URLs für Microsoft Teams, und lassen Sie sie zu. Die Anforderungen finden Sie im folgenden Dokument: [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01.11.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Einschränkungen für Outlook-Add-Ins  <br/> |Um das Outlook-Add-In zu verwenden, müssen Sie sich mit mehrstufiger Authentifizierung (MFA) bei Teams anmelden. Wenn bei der Anmeldung mit MFA ein Fehler auftritt, können Sie sich zwar bei Teams anmelden, aber wenn Sie versuchen, das Add-In zu verwenden, wird eine Fehlermeldung angezeigt.  <br/> Das Add-In ist zurzeit nur für Windows-Benutzer verfügbar.  <br/> Das Add-In funktioniert nicht, wenn Sie einen Authentifizierungsproxy verwenden.  <br/> | Keine Problemumgehung. <br/> |02.08.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams meldet sich immer bei dem in eine Domäne eingebundenen PC-Konto an.   <br/> |Wenn ein Benutzer über zwei verschiedene Microsoft Teams-Konten verfügt und auf seinem Computer der Domänenbeitritt aktiviert ist, verwendet Microsoft Teams das in eine Domäne eingebundene Profil auf dem Computer, um den Benutzer automatisch bei Microsoft Teams anzumelden. Um zu dem anderen Microsoft Teams-Konto zu wechseln, muss der Benutzer sich manuell bei der App abmelden und sich mit Anmeldeinformationen für das zweite Konto anmelden. Wenn sich der Benutzer bei Microsoft Teams abmeldet und den Computer neu startet, meldet Microsoft Teams sich beim Neustart automatisch mit dem in die Domäne eingebundenen Profil an. <br/> | Keine Problemumgehung. <br/> |02.08.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Fehler bei der modernen Authentifizierung – Formularauthentifizierung nicht aktiviert  <br/> |Verwenden Sie bei einem anfänglichen Fehler bei der mehrstufigen Authentifizierung die Web-App für die Authentifizierung.  <br/> Weitere Informationen finden Sie unter [Unterstützung für den Parameter „prompt=login“ für die Active Directory-Verbunddienste (AD FS)](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Überprüfen Sie diese Einstellung: `Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled`.  <br/> |19.06.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Planner in Build mit einmaligem Anmelden (SSO) <br/> |SSO gilt nicht für Planner. Sie müssen sich bei der ersten Verwendung von Planner auf jedem Client erneut anmelden.  <br/> |Keine Problemumgehung. Wir arbeiten an weiteren Verbesserungen für die Authentifizierung.  <br/> |28.02.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Ein Profilbild kann nicht gespeichert werden.  <br/> |Benutzer können ihr Profilbild nicht speichern, wenn das Exchange-Postfach in Exchange 2016 CU2 oder früher lokal gehostet (verwaltet) wird.  <br/> |Keine Problemumgehung.  <br/> |28.02.2017  <br/> |

## <a name="browser"></a>Browser

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Grüne Artefakte beim Videorendering in Chrome  <br/> |Beim Anzeigen von Videos oder Übertragen des Bildschirms in einem Anruf oder MeetUp in Chrome sind grüne Artefakte zu sehen.  <br/> |Deaktivieren Sie die Einstellung für die Hardwarebeschleunigung in Chrome.  <br/> |03.08.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Unterstützung des Webclients in Safari  <br/> |Benutzer, die den Microsoft Teams-Webclient in Safari zu öffnen versuchen, werden aufgefordert, den Desktopclient herunterzuladen. Microsoft überprüft die Safari-Unterstützung und informiert in der [Microsoft Teams-Roadmap](https://aka.ms/TeamsRoadmap) über Updates.  <br/> |Verwenden Sie unterstützte Internetbrowser wie zum Beispiel Internet Explorer 11+, Microsoft Edge 12+, Chrome 51.0+ und Firefox 47.0+.  <br/> |02.11.2016  <br/> |

## <a name="channels"></a>Kanäle

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Wenn ein Benutzer das Unternehmen verlässt, wird er in Microsoft Teams als „Unbekannter Benutzer“ angezeigt.<br/> |Wenn ein Benutzer das Unternehmen verlässt, wird er in Microsoft Teams als „Unbekannter Benutzer“ angezeigt. Außerdem wird auf der Unterhaltungsregisterkarte die folgende Meldung angezeigt: „Unknown user has been added to the team“ (Ein unbekannter Benutzer wurde zum Team hinzugefügt). <br/> |Keine Problemumgehung.  <br/> |12.09.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benutzer können einen bereits vorhandenen Kanalnamen nicht erneut erstellen.  <br/> |Ein erstellter Kanalname kann nicht erneut erstellt werden, selbst dann nicht, wenn er gelöscht wird. Unser System behält diese Daten für Szenarien im Zusammenhang mit dem Schutz von Informationen bei.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Beim Umbenennen eines Kanals in Microsoft Teams wird der entsprechende Ordner in SharePoint Online nicht umbenannt.  <br/> |Wenn ein Kanal in Microsoft Teams umbenannt wird, wird der Ordner für das Team in der Dokumentbibliothek von SharePoint Online nicht entsprechend geändert. Oben auf der Registerkarte „Dateien“ des umbenannten Kanals wird der richtige SharePoint Online-Ordnername angezeigt.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Die URL-Vorschau wird möglicherweise nicht für alle URLs angezeigt.  <br/> |Für einige URLs wird möglicherweise keine Vorschau angezeigt.  Voraussetzung dafür ist, dass die ursprüngliche URL über die Fähigkeit zum Anzeigen einer Vorschau verfügt. <br/> |Keine Problemumgehung. <br/> |01.09.2018 <br/> |

## <a name="chat"></a>Chat

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Erwähnungen für Sendebenachrichtigungen für gelöschte Nachrichten mit Kanallink  <br/> |Es gibt eine bekannte Einschränkung für Benachrichtigungen, wenn Sie in einer Nachricht @erwähnt werden und die Nachricht gelöscht wird. Sie können über die Benachrichtigung im Feed zu dem Kanal navigieren, aber nicht zu einer bestimmten Nachricht. <br/> | Dies ist so vorgesehen. <br/> | 28.03.2017  <br/>|


## <a name="client"></a>Client

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams wird nicht automatisch aktualisiert.   <br/> | Wenn Microsoft Teams mithilfe von Installationsskripts in „Programme“ anstatt im Standardspeicherort installiert wird, wird der Client bei Verfügbarkeit neuer Versionen nicht automatisch aktualisiert.    <br/> | Dies ist so vorgesehen. Achten Sie darauf, die Anwendung im Standardspeicherort zu installieren: `user\Appdata`.  <br/> | 07.09.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Wenn Sie ein Laufwerk symbolisch mit „C:\users“ verknüpfen oder diesem Verzeichnis zuordnen, wird die App mit einem weißen Bildschirm gestartet.  <br/> | Wenn Microsoft Teams mithilfe von Installationsskripts in „Programme“ anstatt im Standardspeicherort installiert wird, wird der Client bei Verfügbarkeit neuer Versionen nicht automatisch aktualisiert.   <br/> | Dies ist so vorgesehen. Achten Sie darauf, die Anwendung im Standardspeicherort zu installieren: `user\Appdata`. Wenn die Zuordnung erforderlich ist, sollten Sie die Webversion von Microsoft Teams verwenden.  <br/> | 07.09.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Wenn Sie ein Laufwerk symbolisch mit „C:\users“ verknüpfen oder diesem Verzeichnis zuordnen, wird die App mit einem weißen Bildschirm gestartet.  <br/> |Wenn der Standardspeicherort von `C:\users\<user>\appData` durch Verschieben des Ordners `C:\users` oder mithilfe einer symbolischen Verknüpfung geändert wird, wird die App mit einem weißen Bildschirm gestartet.   <br/> |Eine Problemumgehung ist nicht bekannt. Wenn die Zuordnung erforderlich ist, sollten Sie die Webversion von Microsoft Teams verwenden.   <br/> |13.03.2017  <br/> |

## <a name="environment"></a>Umgebung

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Gruppenpostfächer sind nicht für Archivierungszwecke (zusätzlicher Speicher) aktiviert.  <br/> |Im Office 365 Security & Compliance Center können globale Administratoren die Archivierung für Gruppenpostfächer nicht aktivieren. Dies ist nur für Benutzerpostfächer möglich.  <br/> |Wenn die Kapazität des Gruppenpostfachs fast erreicht ist, bitten Sie den Microsoft Office-Support, die Postfachgröße zu erweitern.  <br/> |01.02.2017  <br/> |

## <a name="guest-access"></a>Gastzugriff

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Kunden aus der EU und der APAC-Region wird eine Fehlermeldung angezeigt, wenn sie einen Gastbenutzer aus einem anderen Mandanten hinzufügen.    <br/> | Bei Kunden in der EU und in der APAC-Region tritt eine Replikationsverzögerung zwischen Microsoft Teams und Azure Active Directory auf. Wenn Benutzer eines EU- oder APAC-Mandanten versuchen, einen Gastbenutzer aus einem anderen Mandanten hinzuzufügen, werden sie in einer Fehlermeldung aufgefordert, es erneut zu versuchen.   <br/> |Klicken Sie erneut auf die Schaltfläche zum Wiederholen, um den Gastbenutzer hinzuzufügen.  <br/> |08.11.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Für von Gästen erstellte Kanäle wird kein Wiki erstellt.  <br/> |Wenn Gäste einen neuen Kanal erstellen, wird die **Wiki**-Registerkarte nicht erstellt. Es gibt keine Möglichkeit, eine **Wiki**-Registerkarte manuell an den Kanal anzufügen. <br/> |Keine Problemumgehung.  <br/> |20.09.2017  <br/>|

## <a name="meetings"></a>Besprechungen

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benutzer können nicht auf Besprechungen/Connectors zugreifen, verfügen aber über Exchange Online-Postfächer. <br/> |Ein Kunde blockiert aktiv EWS für Dienste in Exchange Online, jedoch muss Microsoft Teams mit den EWS-Richtlinien konform sein. <br/> |Damit Microsoft Teams konform ist, müssen Sie die folgenden Zeichenfolgen des Benutzer-Agents für Microsoft Teams innerhalb von EWSAllowList hinzufügen: `SkypeSpaces/*` und `MicrosoftNinja/*`, einschließlich Sternchen. Der folgende Befehl kann verwendet werden: `Set-organizationconfig -EwsAllowList @{Add="MicrosoftNinja/*","SkypeSpaces/*"}`<br/> Weitere Informationen finden Sie unter https://docs.microsoft.com/powershell/module/exchange/organization/Set-OrganizationConfig?view=exchange-ps. <br/> |30.05.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Für manche Besprechungen ist Skype for Business erforderlich.  <br/> |Ihr Terminkalender wird in Microsoft Teams angezeigt. Um an einer Besprechung teilzunehmen, klicken Sie auf die Schaltfläche **Teilnehmen**. <br/> Solange die Entwicklung in diesem Bereich noch nicht abgeschlossen ist, gilt Folgendes: Wenn die Besprechung mit Skype for Business geplant wurde und Sie auf **Teilnehmen** klicken, wird Ihr Skype for Business-Client gestartet, um Sie an der Besprechung teilnehmen zu lassen. Besprechungen, die in Microsoft Teams geplant wurden, werden direkt im Produkt initiiert.  <br/> Diese Funktion wird in Zukunft optimiert.  <br/> |Klicken Sie auf **Teilnehmen**. Microsoft Teams entscheidet anhand der URL aus der Besprechungsbeschreibung selbst, ob Skype for Business für die Teilnahme des Benutzers an der Besprechung erforderlich ist.  <br/> |13.03.2017  <br/> |


|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Maximale Teilnehmeranzahl für Besprechungen  <br/> |Jede Microsoft Teams-Besprechung kann maximal 80 Teilnehmer enthalten.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Besprechungen sind nicht verfügbar.  <br/> |Die Besprechungsfunktion ist nicht verfügbar, wenn das Exchange-Postfach in früheren Versionen als Exchange 2016 CU3 lokal gehostet (verwaltet) wird.  <br/> |Führen Sie ein Upgrade der lokalen Bereitstellung auf Exchange 2016 CU3 oder höher aus.  <br/> |28.02.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Kein Audio beim Freigeben von Inhalten während einer Livekonferenz  <br/> |Beim Freigeben von Inhalten während einer Livekonferenz können die Teilnehmer das Audio des freigegebenen Inhalts (YouTube-Link oder gespeicherte Videodatei) nicht hören.  <br/> |Dies ist nicht vorgesehen.  Microsoft Teams unterstützt zurzeit kein Audio bei der Inhaltsfreigabe.  <br/> |09.10.2018  <br/> |

## <a name="mobile"></a>Mobil

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Automatisch als Favoriten festgelegten Kanäle werden nicht angezeigt.  <br/> |Einige Mitglieder können automatisch als Favoriten festgelegte Kanäle in der mobilen App nicht sehen.  <br/> |Die Mitglieder müssen sich erst bei der Desktop- oder Web-App anmelden, um automatisch als Favoriten festgelegten Kanäle in ihrer mobilen App zu sehen.  <br/> |30.04.2018  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benutzer können möglicherweise auf mit Intune verwalteten mobilen Geräten nicht zwischen Konten wechseln.  <br/> |Benutzer können möglicherweise auf mit Intune verwalteten mobilen Geräten nicht zwischen Konten wechseln.  <br/> |Keine Problemumgehung.  <br/> |20.09.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|In der mobilen App ist es nicht möglich, die Auswahl für Lustiges zu verwenden oder Giphys oder Aufkleber zu verwenden.  <br/> |Sie können in den mobilen Clients keine GIF-Dateien, Emojis oder Aufkleber verwenden.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Layoutunterschiede im mobilen Microsoft Teams-Client  <br/> |Im mobilen Client werden Teams in alphabetischer Reihenfolge angezeigt, und die Kanäle können nicht reduziert werden.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/>|


## <a name="people"></a>Kontakte

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benutzerprofilfotos  <br/> | Microsoft Teams verfügt zurzeit nicht über einen Mechanismus, mit dem verhindert werden kann, dass Benutzer Fotos ändern. Das BTS-Team hat sich mit dem Entwicklungsteam getroffen, das den folgenden Vorschlag eingereicht hat: Funktion 108874: IT-Richtlinie zum Deaktivieren des Hochladens von Profilfotos.   <br/> | Wenn Sie die Möglichkeit wünschen, das Hochladen von Profilfotos in Microsoft Teams zu verhindern, geben Sie hier in den Kommentaren Ihre Stimme ab, und beschreiben Sie ein Geschäftsszenario: https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos <br/> |01.03.2017 <br/> |

## <a name="provisioning"></a>Bereitstellung

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Für eine SharePoint-Website für Microsoft Teams wird ein falscher SharePoint-Benutzer erstellt.  <br/> |Als SharePoint-Ersteller einer Microsoft Teams-Gruppe wird nicht der richtige Benutzer, sondern ein SharePoint-Administrator angezeigt.  <br/> Beim Hinzufügen von Überwachung über die SharePoint-Verwaltungskonsole ist der SharePoint-Administrator der Ersteller für die Seite der Websitesammlung, die der Office 365-Gruppe zugeordnet ist, die für das Team in Microsoft Teams erstellt wird.  <br/> |Keine Problemumgehung.  <br/> |21.07.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benutzer können kein Team erstellen.  <br/> |Möglicherweise hat Ihre Firma eine Richtlinie festgelegt, mit der eingeschränkt wird, wer Office 365-Gruppen oder Teams erstellen kann.  <br/> |Erkundigen Sie sich bei Ihrem IT-Administrator nach der Richtlinie Ihrer Firma für das Erstellen von Gruppen und Teams.  <br/> |13.03.2017  <br/> |

## <a name="skype-for-business-to-teams-upgrade"></a>Upgrade von Skype for Business auf Microsoft Teams

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|

## <a name="tabs"></a>Registerkarten

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Website-Registerkarte führt bei Kunden zu Verwirrung.  <br/> |Website-Registerkarten sind nicht mit dem Browser zu verwechseln. Eine Reihe von Websites, insbesondere solche, die Authentifizierung erfordern oder Popups verwenden, funktionieren nicht, wenn sie als Website-Registerkarte angeheftet werden.  <br/> |Wir arbeiten daran, die Benutzeroberfläche zu verbessern, damit dies für Kunden besser erkennbar ist.  <br/> |02.05.2018  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Seit der Aktivierung des bedingten Zugriffs funktionieren Registerkarten nicht mehr. <br/> |Einige Registerkarten werden möglicherweise im Desktopclient nicht mehr geladen, seit im Mandanten bedingter Zugriff aktiviert wurde. Bei Verwendung des Webclients werden die Registerkarten geladen. Davon können unter anderem die folgenden Registerkarten betroffen sein: „Power BI“, „Formulare“, „VSTS“, „PowerApps“ und „SharePoint-Liste“.  <br/> |Um die betroffenen Registerkarten anzuzeigen, müssen Sie Microsoft Teams in Microsoft Edge, Internet Explorer oder Chrome verwenden, und die Erweiterung für Windows 10-Konten muss installiert sein. Für einige Registerkarten ist weiterhin die Webauthentifizierung erforderlich, die im Desktopclient nicht funktioniert, wenn eine Zertifizierungsstelle aktiviert ist. Wir arbeiten gemeinsam mit Partnern daran, diese Szenarien zu ermöglichen. Bisher haben wir Planner, OneNote und Stream aktiviert. <br/> |05.04.2018  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Die Liste der Arbeitsbereiche ist nicht alphabetisch sortiert.  <br/> |Wenn Benutzer eine Power BI-Registerkarte hinzufügen und dabei zwischen Arbeitsbereichen wechseln, wird eine nicht alphabetisch sortierte Liste der Arbeitsbereiche, zwischen denen sie wechseln können, angezeigt.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Die Scrollleiste wird beim Auswählen von Berichten nicht mehr angezeigt.  <br/> |Benutzer können beim Hinzufügen von Power BI-Berichten nicht durch eine Liste mit Berichten scrollen, die nicht auf den Bildschirm passt, ohne die Scrollleiste zu verlieren.  <br/> |Scrollen Sie mit der NACH-OBEN- und der NACH-UNTEN-TASTE durch die Liste.  <br/> |13.03.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Integration zwischen Microsoft Teams und Planner mit der Onlineversion von Planner <br/> |Aufgabenbuckets in Planner werden in der Onlineversion von Planner nicht angezeigt.  <br/> |Keine Problemumgehung. <br/> |28.02.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Eine SharePoint-Registerkartenseite wird als leerer Bildschirm dargestellt. <br/> |Benutzerdefinierte SharePoint Online-Domänen werden zurzeit nicht unterstützt. Wenn Benutzer versuchen, eine SharePoint-Registerkartenseite hinzuzufügen, wird ein leerer Bildschirm angezeigt. <br/> |Keine Problemumgehung. <br/> |20.08.2018  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Legacy-OneNote-Registerkarte  <br/> |Legacy-OneNote-Registerkarten, die während der öffentlichen Vorschau von Microsoft Teams erstellt wurden, können nicht umbenannt oder gelöscht werden.  <br/> |Keine Problemumgehung. <br/> |08.11.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Suchfunktion in der SharePoint-Listenregisterkarte  <br/> |Wenn Sie versuchen, eine Datei über die Suchfunktion der SharePoint-Listenregisterkarte zu öffnen, wird die Eingabeaufforderung "Sie benötigen eine neue App, um diese Info zu öffnen" ausgelöst, und die Datei wird nicht geöffnet. <br/> |Öffnen Sie die Datei direkt aus der Liste statt über die Suchleiste. <br/> |11.2.2019  <br/> |

## <a name="teams"></a>Teams

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Überwachungsprotokolle melden möglicherweise einen falschen Benutzernamen als Initiator, wenn jemand aus einem Team entfernt wurde.  <br/> |Ein Team aus Microsoft Teams entspricht in AAD einer modernen Gruppe. Wenn Sie über die Microsoft Teams-Benutzeroberfläche ein Mitglied hinzufügen bzw. entfernen, ist genau bekannt, welcher Benutzer die Änderung initiiert hat, und das Überwachungsprotokoll gibt die richtigen Informationen wieder. Wenn jedoch ein Benutzer über AAD ein Mitglied entfernt oder hinzufügt, wird die Änderung mit dem Microsoft Teams-Back-End synchronisiert, ohne dass Microsoft Teams erfährt, wer die Aktion initiiert hat. Microsoft Teams sucht den ersten Besitzer des Teams als Initiator aus. Dies geht letztendlich auch aus dem Überwachungsprotokoll hervor.    <br/> |  <br/> |11.05.2018  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Der Upload von Fotos in Microsoft Teams wird in OWA/Outlook nicht gemäß der Richtlinie blockiert.   <br/> | Microsoft Teams lässt zu, dass Benutzer Fotos direkt in Office 365 hochladen, obwohl Richtlinieneinstellungen vorhanden sind, die Fotouploads für OWA verhindern.   <br/> |<br/>  |16.10.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|In der Liste der öffentlichen Teams werden nicht alle Teams angezeigt.  <br/> |Die Liste der öffentlichen Teams basiert auf Microsoft Graph.  <br/> |Wenn Sie ein Team nicht sehen, suchen Sie es rechts oben im Suchfeld. Außerdem sollten die Teambesitzer ihren Kollegen die Teamnamen mitteilen, da die Suchergebnisse möglicherweise viele Teamnamen enthalten. <br/> | 21.07.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Teamnamen mit Sonderzeichen können zu Fehlern beim Erstellen von Besprechungen führen.  <br/> |Benutzern wird in Rot die Fehlermeldung **error has occured** (Ein Fehler ist aufgetreten) angezeigt, wenn sie versuchen, eine Besprechung für ein Team zu erstellen, dessen Name Sonderzeichen enthält.   <br/> |Benennen Sie das Team um, oder erstellen Sie ein neues Team mit einem Namen, in dem das Zeichen „/“ nicht enthalten ist.  <br/> |13.07.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Der Connector funktioniert nicht, wenn Teamnamen das Zeichen „&amp;“ enthalten.  <br/> |Wenn ein Teamname mit dem Zeichen „&amp;“ erstellt wird, können Connectors im Team bzw. in der Gruppe nicht eingerichtet werden.  <br/> |Verwenden Sie in Teamnamen keine Sonderzeichen.  <br/> |21.06.17  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Maximale Anzahl von 5000 Mitgliedern pro Team  <br/> |Jedes Team in Microsoft Teams kann maximal 5000 Mitglieder enthalten.  <br/> |Keine Problemumgehung.  <br/> |6.2.2019  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Beim Löschen eines Teams wird auch die zugeordnete Gruppe gelöscht.  <br/> |Benutzer wissen möglicherweise nicht, dass zusammen mit dem Team auch die zugrunde liegende Office 365-Gruppe gelöscht wird. Außerdem wird, wenn die zugrunde liegende Office 365-Gruppe gelöscht wird, auch das Team gelöscht.  <br/> |Diese Informationen werden in zusätzlichen Benutzermeldungen in Microsoft Teams angezeigt. Auf der Benutzeroberfläche von Office 365-Gruppen werden diese Informationen nicht angezeigt. Ihr Helpdesk kann gelöschte Gruppen oder Teams wiederherstellen.  <br/> |13.03.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|In der Microsoft Teams-Desktop-App wird ein weißer Bildschirm angezeigt.  <br/> | <br/> |Versuchen Sie, den Grafiktreiber auf dem Computer zu löschen oder neu zu installieren, oder starten Sie Microsoft Teams über eine Befehlszeile mit einem Flag zum Deaktivieren der GPU:<ul><li>Windows: Öffnen Sie die Eingabeaufforderung, und geben Sie Folgendes ein: `cd %localappdata%\microsoft\teams\current run Teams.exe --disable-gpu`</li><li>Mac: Starten Sie Terminal, und geben Sie Folgendes ein: `cd \Applications folder Microsoft\ Teams.app/Contents/MacOS/Teams --disable-gpu`</li></ul> <br/> |<br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benutzer erhält keine Willkommens-E-Mail, wenn er durch den Administrator hinzugefügt wird.  <br/> |Wenn Sie ein Mitglied mit PowerShell oder über das Teams Admin Center zu einem Team hinzufügen, erhalten Sie keine Willkommens-E-Mail von Microsoft Teams.  <br/> |Wenn Sie ein Mitglied direkt über die Teams-Benutzeroberfläche hinzufügen, wird eine E-Mail gesendet. Derzeit gibt es keine Problemumgehung beim Durchführen dieser Aufgabe durch den Administrator.  <br/> |12.2.19  <br/> |
