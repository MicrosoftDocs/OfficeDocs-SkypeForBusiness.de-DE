---
title: Bekannte Probleme für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: marcl
search.appverid: MET150
description: Aktuelle Liste der bekannten Probleme für die Microsoft Teams-Client-App und Administratorfunktionen.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d8b1497a864a1dbd271af81363151275ffe7de1e
ms.sourcegitcommit: 8a4ed16adc60497510a528784e139075fbae9e55
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "25502232"
---
# <a name="known-issues-for-microsoft-teams"></a>Bekannte Probleme für Microsoft Teams

In diesem Artikel werden die bekannten Probleme für Microsoft-Teams, nach Funktionsbereich.

## <a name="administration"></a>Verwaltung

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Überwachungsprotokolle können eine falsche Benutzername als Initiator melden, wenn eine Person aus einem Team entfernt wurde  <br/> |Teams Team ist eine moderne Gruppe in AAD. Wenn Sie ein Element über die Benutzeroberfläche des Teams Software, der Fluss weiß genau mit der der Benutzer die Änderung initiiert, und das Überwachungsprotokoll die korrekte Informationen widerspiegelt. Jedoch, wenn ein Benutzer fügt/Mitglied über AAD entfernt, wird die Änderung synchronisiert an die Teams Back-End-ohne Teams, die die Aktion initiiert hat. Microsoft-Teams, wählt den ersten Besitzer des Teams als der Initiator, der in das Überwachungsprotokoll sowie schließlich wiedergegeben wird.    <br/> |  <br/> |5/11/18  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|EAF Richtlinie in der erweiterten Risikominderung Experience Toolkit (EMET) kann nicht richtig Chrom Sandkasten Optimierungen als Bedrohung identifizieren. <br/> |Es besteht ein Problem mit Chrom Sandkasten, in dem die Richtlinie exportieren Adresse Tabelle Access Filtern (EAF) in der erweiterten Risikominderung Experience Toolkit (EMET) falsch Chrom Sandkasten Optimierungen als Bedrohung identifizieren kann. Die Registerkarten in der Webansicht Teams verhindert, dass das ordnungsgemäß gerendert wird. <br/> | EAF für Chrome deaktivieren. Lesen Sie mehr über das Problem [EMET Gegenmaßnahmen Richtlinien](https://support.microsoft.com/en-us/help/2909257/emet-mitigations-guidelines) <br/> |10/11/18 <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Hinzufügen von Mitgliedern zu Teams bei UsersPermissionToReadOtherUsersEnabled auf False festgelegt ist nicht möglich  <br/> |Wenn dieser Wert wird in AAD auf False festgelegt, Kunden nicht an externe/interne Mitglieder im Microsoft-Teams hinzuzufügen kann und die folgende Fehlermeldung wird angezeigt: "Es konnte nicht Mitglied hinzugefügt. Wir haben ein Problem ausgeführt. Versuchen Sie es später erneut." Mitglieder können jedoch direkt zu Office 365-Gruppen hinzugefügt werden.    <br/> |Diese Einstellung auf "true" in AAD geändert.  <br/> |4/10/18  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Admin-Verwaltung von Mandanten geltende Connectors ist nicht mehr verfügbar  <br/> |Beim Hinzufügen eines Connectors im Client und online-Version werden wir den Fehler: ein unerwarteter Fehler aufgetreten. Versuchen Sie es erneut. Set-OrganizationConfig - ConnectorsEnabled = True   <br/> |Deaktivieren Sie mit Einstellungen für Teams. Finden Sie unter Support-Artikelhttps://msdn.microsoft.com/microsoft-teams/connectors  <br/> |21.06.2017  <br/> |

## <a name="apps"></a>Apps

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Connector-Optionen für manche Teams fehlt.  <br/> |Wenn Sie mit der rechten Maustaste auf einen Kanal klicken, ist die Option für Connectors für keines der Teammitglieder vorhanden.  <br/> |Der Ersteller des Teams benötigt ein Onlinepostfach, andernfalls ist keine Connector-Option verfügbar. Dieses Verhalten ist zu erwarten.  <br/> |26.06.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|"Assignments" app bleibt Visble Wenn deaktiviert  <br/> |Wenn die app "Aufgaben" in der Verwaltungskonsole deaktiviert ist, bleibt sie innerhalb des Teams-Clients für EDU lizenzierte Benutzer sichtbar. Auswählen, wenn deaktiviert gibt einen Fehler zurück, der angibt, "Galerie zurück. Ist ein Fehler aufgetreten..."  <br/> |Keine Problemumgehung  <br/> |12/29/17  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Kann nicht als Teambesitzer Connectors löschen  <br/> |Versuch, eine Verbindung als Besitzer löschen können, die andernfalls eine Connector hinzufügen, während "Zulassen, dass Mitglieder zu erstellen, aktualisieren und Entfernen von Connectors" deaktivierte löst ist ein Fehler, der angibt, des Benutzers nicht über die Berechtigung dazu. <br/> |Vorübergehende aktivieren "Zulassen, dass Mitglieder zu erstellen, aktualisieren und Entfernen von Connectors" ansetzt, kann der Besitzer des Connectors löschen.  <br/> |7/27/18  <br/> |

## <a name="audio-conferencing"></a>Audiokonferenz

|**Problem**|**Verhalten/Symptome**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|PSTN-Anrufer mit der gleichen „Von"-Nummer werden in der Teilnehmerliste der Besprechung als derselbe Benutzer angezeigt.  <br/> |Wenn mehrere PSTN-Anrufer an einer Besprechung teilnehmen und ihre Anrufer-IDs als eine einzige Nummer gekennzeichnet sind, werden diese Anrufer in der Teilnehmerliste der Besprechung als ein einziger Anrufer angezeigt.  <br/> |Keine Problemumgehung  <br/> |25.9.2017  <br/> |
|Der Bereich mit den Besprechungsinformationen wird zeitweise nicht angezeigt.  <br/> |Der Bereich mit den Besprechungsinformationen wird im Teams-Client möglicherweise nicht angezeigt, wenn Benutzer versuchen, Telefonnummern einer Konferenzbrücke oder Konferenzkennungen nachzuschlagen.  <br/> |Sie können die Telefonnummern einer Konferenzbrücke oder Konferenzkennungen in den Besprechungsdetails oder im Outlook-Kalender anzeigen.  <br/> |25.9.2017  <br/> |
|Besprechungseinladungen über das Outlook-Add-In enthalten sinnlose Zeichen in PSTN-Koordinaten für Nicht-US-Gebietsschemas.  <br/> |Beim Planen von privaten Besprechungen mit dem Outlook-Add-In für Microsoft Teams auf einem Computer mit Nicht-US-Gebietsschemas enthalten PSTN-Koordinaten möglicherweise sinnlose Zeichen.  <br/> |Keine Problemumgehung  <br/> |25.9.2017  <br/> |
|Bei der Auswahl müssen mindestens fünf Ziffern verwendet werden.  <br/> |Benutzer, die aus einer Besprechung eine Nummer zu wählen versuchen, müssen mindestens fünf Ziffern eingeben, obwohl eine Wählplan-Normalisierungsregel verfügbar ist, durch die gewählte kurze Nummern in E.164 normalisiert werden.  <br/> |Geben Sie bei der Auswahl anstelle der internen Durchwahlnummer die Nummer im vollständigen Durchwahlnummernformat oder lokalen Nummernformat ein.  <br/> |25.9.2017  <br/> |
|Das Auswahlsteuerelement wird zeitweise nicht angezeigt.  <br/> |Das Auswahlsteuerelement ist möglicherweise im Bereich mit den Besprechungsinformationen nicht sichtbar.  <br/> |Keine Problemumgehung  <br/> |25.9.2017  <br/> |
|Statische Konferenzkennungen werden für Microsoft Teams-Besprechungen nicht unterstützt.  <br/> |Wenn der Administrator die Standardeinstellung außer Kraft setzt und sie von einer dynamischen Konferenzkennung in eine statische Konferenzkennung ändert, wird diese Einstellung für Microsoft Teams-Besprechungen nicht wirksam. Finden Sie unter [Audiokonferenzen mithilfe von dynamischen IDs in Ihrer Organisation](/skypeforbusiness/audio-conferencing-in-office-365/using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Keine Problemumgehung  <br/> |25.9.2017  <br/> |
|PSTN-Besprechungs-Koordinaten sind nicht verfügbar für Benutzer von Skype-for-Business  <br/> |Wenn es sich bei dem Benutzer um einen lokalen Skype-for-Business-Benutzer handelt, der mit Lizenzen für Skype-for-Business Online, Audiokonferenzen und Teams ausgestattet ist, enthalten alle Meetings, die mit Teams geplant sind, keine PSTN-Meeting-Koordinaten. <br/> |Keine Problemumgehung  <br/> |01.02.2018  <br/> |

## <a name="authentication"></a>Authentifizierung

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Wenn Sie Microsoft Teams über Internet Explorer oder Microsoft Edge beitreten, entsteht im Programm eine Dauerschleife, oder das Programm stürzt ab, und die Anmeldung funktioniert nicht.   <br/> | Ihre Organisation nutzt die Option „Vertrauenswürdige Sites“ in Internet Explorer, und die Anmeldung über die webbasierte Microsoft Teams-Anwendung funktioniert nicht richtig, da vertrauenswürdige Sites für Microsoft Teams nicht zulässig sind. <br/>|Nehmen Sie mit Administratorrechten oder über ein Gruppenrichtlinienobjekt die folgenden Änderungen an den Internet Explorer-Einstellungen vor:<br/><ol><li>Klicken Sie unter **Internetoptionen** &gt; **Privacy** &gt; **Erweitert**, erste Teilnehmern und Drittanbieter-Cookies annehmen, und aktivieren Sie das Kontrollkästchen für **immer Cookies Sitzung**.</li><li>Klicken Sie auf **Internetoptionen** &gt; **Vertrauenswürdige Sites** &gt; **Sites**, und fügen Sie die folgenden:<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>HINWEIS</b>: Validieren Sie immer alle vertrauenswürdigen URLs für Microsoft Teams, und lassen Sie sie zu. Die Anforderungen finden Sie im folgenden Dokument: [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01.11.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Einschränkungen für Outlook-Add-Ins  <br/> |Um das Outlook-Add-In zu verwenden, müssen Sie sich mit mehrstufiger Authentifizierung (MFA) bei Teams anmelden. Wenn bei der Anmeldung mit MFA ein Fehler auftritt, können Sie sich zwar bei Teams anmelden, aber wenn Sie versuchen, das Add-In zu verwenden, wird eine Fehlermeldung angezeigt.  <br/> Das Add-In ist zurzeit nur für Windows-Benutzer verfügbar.  <br/> Das Add-In funktioniert nicht, wenn Sie einen Authentifizierungsproxy verwenden.  <br/> | Keine Problemumgehung. <br/> |02.08.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Microsoft-Teams, wird immer die Domäne PC-Konto anmelden.   <br/> |Wenn ein Benutzer hat zwei Konten für Teams und verfügt über einen Computer mit Domäne aktiviert, Teams werden das Domäne eingebundener-Profil auf dem Computer verwenden, um automatisch die Anmeldung des Benutzers in Teams. Um an das andere Teams Konto zu wechseln, muss der Benutzer manuell die app abmelden und geben Sie Anmeldeinformationen für das zweite Konto anzumelden. Wenn der Benutzer meldet sich außerhalb des Teams und den Computer nach dem Neustart startet werden automatisch Teams melden Sie sich mit der Domäne beigetreten Profil. <br/> | Keine Problemumgehung. <br/> |02.08.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Moderne Authentifizierungsfehler - Formularauthentifizierung nicht aktiviert  <br/> |Verwenden Sie bei einem anfänglichen Fehler bei der mehrstufigen Authentifizierung die Web-App für die Authentifizierung.  <br/> Weitere Informationen finden Sie unter [Unterstützung für den Parameter „prompt=login“ für die Active Directory-Verbunddienste (AD FS)](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Aktivieren Sie diese Einstellung: `Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled`.  <br/> |19.06.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Planner für einmaliges Anmelden (SSO) build <br/> |SSO gilt nicht für Planner. Sie müssen sich bei der ersten Verwendung von Planner auf jedem Client erneut anmelden.  <br/> |Keine Problemumgehung. Wir arbeiten an weiteren Verbesserungen für die Authentifizierung.  <br/> |28.02.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Ein Profilbild kann nicht gespeichert werden.  <br/> |Benutzer können nicht das Profilbild gespeichert werden, wenn das Exchange-Postfach gehosteten () lokal auf Exchange 2016 CU2 oder niedriger ist.  <br/> |Keine Problemumgehung.  <br/> |28.02.2017  <br/> |

## <a name="browser"></a>Browser

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Grüne Artefakte beim Videorendering in Chrome  <br/> |Grüne Artefakte beim Anzeigen von Video oder Freigabe den Bildschirm im Gespräch oder Meetup in Chrome angezeigt werden.  <br/> |Deaktivieren Sie die Einstellung für die Hardwarebeschleunigung in Chrome.  <br/> |03.08.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Unterstützung des Webclients in Safari  <br/> |Benutzer, die den Microsoft Teams-Webclient in Safari zu öffnen versuchen, werden aufgefordert, den Desktopclient herunterzuladen. Microsoft überprüft die Safari-Unterstützung und informiert in der [Microsoft Teams-Roadmap](https://aka.ms/TeamsRoadmap) über Updates.  <br/> |Verwendung Internetbrowser, einschließlich unterstützt: Internet Explorer 11 +, Microsoft Edge 12 +, Chrome 51.0 + und Firefox 47.0 +.  <br/> |2.11.2016  <br/> |

## <a name="channels"></a>Kanäle

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Wenn ein Benutzer das Unternehmen verlässt, wird sie im Microsoft-Teams, als "Unbekannte Benutzer"<br/> |Wenn ein Benutzer das Unternehmen verlässt, wird sie im Microsoft-Teams, als "Unbekannte Benutzer". Zusätzlich wird auf die Registerkarte Unterhaltung angezeigt: "Unbekannte Benutzer wurde hinzugefügt, das Team." <br/> |Keine Problemumgehung  <br/> |9/12/17  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benutzer können einen bereits vorhandenen Kanalnamen nicht erneut erstellen.  <br/> |Ein erstellter Kanalname kann nicht erneut erstellt werden, selbst dann nicht, wenn er gelöscht wird. Unser System behält diese Daten für Szenarien im Zusammenhang mit dem Schutz von Informationen bei.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Umbenennen eines Kanals in Microsoft-Teams, werden den entsprechenden Ordner in SharePoint Online nicht umbenannt  <br/> |Wird ein Kanal in Microsoft-Teams, umbenannt, wird der Ordner in der SharePoint Online-Dokumentbibliothek, die an das Team entspricht nicht entsprechend geändert. Die richtigen SharePoint Online Ordnername wird am oberen Rand der Registerkarte umbenannte Channel Dateien angezeigt.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/> |

## <a name="chat"></a>Chat

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|@ Erwähnungen für gelöschte Nachricht senden die Benachrichtigung mit Channel-link  <br/> |Es ist eine Benachrichtigung bekannte Einschränkung bei unter erwähnten in einer Nachricht, der gelöscht wird; die Benachrichtigung in den Feed navigiert für den DDE-Kanal, jedoch nicht für eine bestimmte Nachricht. <br/> | Entwurfsbedingt <br/> | 3/28/17  <br/>|


## <a name="client"></a>Client

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Teams wird nicht automatisch aktualisiert.   <br/> | Wenn Microsoft-Teams auf Programmdateien mithilfe von Installationsskripts und nicht am Standardspeicherort installiert ist, der Client nicht automatisch aktualisieren, neue Versionen verfügbar sind.    <br/> | Verhalten ist erwünscht. Achten Sie darauf, um die Anwendung am Standardspeicherort zu installieren: `user\Appdata`.  <br/> | 7/9/17  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Symlink oder Mappying ein Laufwerk C:\users bewirkt, dass die app Weißer Bildschirm Start  <br/> | Wenn Microsoft-Teams auf Programmdateien mithilfe von Installationsskripts und nicht am Standardspeicherort installiert ist, der Client nicht automatisch aktualisieren, neue Versionen verfügbar sind.   <br/> | Verhalten ist erwünscht. Achten Sie darauf, um die Anwendung am Standardspeicherort zu installieren: `user\Appdata`. Wenn die Zuordnung vorhanden sein muss, sollten Sie die Webversion von Microsoft-Teams verwenden.  <br/> | 7/9/17  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Symlink oder zum Zuordnen von einem Laufwerk zu c:\users verursacht app Weißer Bildschirm Start  <br/> |Wenn der Standardspeicherort des `C:\users\<user>\appData` wird durch Verschieben geändert die `C:\users` Ordner oder Symlink verwenden, wird die app mit einem weißen Bildschirm gestartet.   <br/> |Es kann keine bekannten umgangen werden. Wenn die Zuordnung vorhanden sein muss, sollten Sie die Webversion von Microsoft-Teams verwenden.   <br/> |13.03.2017  <br/> |

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
|Benutzer können nicht Zugriff auf Besprechungen-Connectors jedoch über Exchange Online-Postfächer. <br/> |Kunden aktiv blockiert EWS von Diensten in Exchange Online muss jedoch innerhalb der EWS-Richtlinien kompatibel MS-Teams haben. <br/> |Damit MS-Teams kompatibel ist, müssen Sie die folgende Zeichenfolge des Benutzer-Agent für MS-Teams innerhalb der EWSAllowList hinzufügen: `*skypespaces*`, einschließlich Sternchen. Der vollständige Befehl ist:`set-organizationconfig -ewsallowlist *skypespaces*`<br/> Weitere Informationen:https://docs.microsoft.com/powershell/module/exchange/organization/Set-OrganizationConfig?view=exchange-ps <br/> |5/30/17  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Für manche Besprechungen ist Skype for Business erforderlich.  <br/> |Ihr Terminkalender wird in Microsoft Teams angezeigt. Um an einer Besprechung teilzunehmen, klicken Sie auf die Schaltfläche **Teilnehmen**. <br/> Solange die Entwicklung in diesem Bereich noch nicht abgeschlossen ist, gilt Folgendes: Wenn die Besprechung mit Skype for Business geplant wurde und Sie auf **Teilnehmen** klicken, wird Ihr Skype for Business-Client gestartet, um Sie an der Besprechung teilnehmen zu lassen. Besprechungen, die in Microsoft Teams geplant wurden, werden direkt im Produkt initiiert.  <br/> Diese Funktion wird in Zukunft optimiert.  <br/> |Klicken Sie auf **Teilnehmen**. Microsoft Teams entscheidet anhand der URL aus der Besprechungsbeschreibung selbst, ob Skype for Business für die Teilnahme des Benutzers an der Besprechung erforderlich ist.  <br/> |13.03.2017  <br/> |


|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Maximale Teilnehmeranzahl für Besprechungen  <br/> |Jede Microsoft Teams-Besprechung kann maximal 80 Teilnehmer enthalten.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Besprechungen sind nicht verfügbar.  <br/> |Meeting-Funktionalität ist nicht verfügbar, wenn Exchange-Postfach gehosteten () lokal in der Version Exchange 2016 CU3 kleiner ist.  <br/> |Führen Sie ein Upgrade der lokalen Bereitstellung auf Exchange 2016 CU3 oder höher aus.  <br/> |28.02.2017  <br/> |

## <a name="mobile"></a>Mobil

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Kann nicht automatisch favorisierte Kanäle finden Sie unter  <br/> |Einige Member können automatische favorisierte Kanäle auf dem mobilen app finden Sie unter nicht.  <br/> |Mitglieder müssen auf dem Desktop oder Web app erstmaligen Anmelden bei automatische favorisierte Kanäle auf ihren mobilen app angezeigt.  <br/> |4/30/18  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benutzer können möglicherweise auf mit Intune verwalteten mobilen Geräten nicht zwischen Konten wechseln.  <br/> |Benutzer können möglicherweise auf mit Intune verwalteten mobilen Geräten nicht zwischen Konten wechseln.  <br/> |Keine Problemumgehung.  <br/> |20.09.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Kann nicht verwendet Spaß Personenauswahl oder Giphys oder Aufkleber in mobilen app  <br/> |Sie können keine GIF-Dateien, Emojis oder Aufkleber auf mobilen Clients verwenden.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Unterschiede bei der Mobile Client Teams Layout  <br/> |Teams sind in alphabetischer Reihenfolge aufgeführt und die Kanäle nicht auf dem mobilen Client reduziert werden.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/>|


## <a name="people"></a>Personen

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Profil Benutzerfotos  <br/> | Derzeit Teams verfügt nicht über einen Mechanismus, um Benutzer daran zu hindern, Fotos ändern. Das Team BTS wurde mit dem Entwicklungsteam, die Folgendes für Erwägung einreicht erzielt: Feature 108874: IT-Richtlinien zum Hochladen von Fotos Profil deaktivieren   <br/> | Wenn Sie Kunden die Möglichkeit haben, zu verhindern, dass Fotos Profil in Teams hochladen möchten, haben sie ihre Stimme und Business Case hier Kommentare hinzufügen:https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos
 <br/> |3/1/17 <br/> |

## <a name="provisioning"></a>Bereitstellung

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Für eine SharePoint-Website für Microsoft Teams wird ein falscher SharePoint-Benutzer erstellt.  <br/> |Als SharePoint-Ersteller einer Microsoft Teams-Gruppe wird nicht der richtige Benutzer, sondern ein SharePoint-Administrator angezeigt.  <br/> Beim Hinzufügen von Überwachung über die SharePoint-Verwaltungskonsole ist der SharePoint-Administrator der Ersteller für die Seite der Websitesammlung, die der Office 365-Gruppe zugeordnet ist, die für das Team in Microsoft Teams erstellt wird.  <br/> |Keine Problemumgehung.  <br/> |21.07.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Benutzer können kein Team erstellen.  <br/> |Möglicherweise hat Ihre Firma eine Richtlinie festgelegt, mit der eingeschränkt wird, wer Office 365-Gruppen oder Teams erstellen kann.  <br/> |Erkundigen Sie sich bei Ihrem IT-Administrator nach der Richtlinie Ihrer Firma für das Erstellen von Gruppen und Teams.  <br/> |13.03.2017  <br/> |

## <a name="tabs"></a>Registerkarten

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Website-Registerkarte, was zu Verwirrung führt Kunden  <br/> |Website-Registerkarten sind nicht gleichbedeutend mit Ihrem Browser. Eine Anzahl von Websites, insbesondere solche, die eine Authentifizierung erforderlich ist, oder verwenden Popups, funktionieren nicht, wenn als Website Registerkarte fixiert.  <br/> |Wir arbeiten auf die Verbesserung der Benutzeroberfläche, um für Kunden klarer zu machen.  <br/> |5/2/18  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Registerkarten nicht funktionsfähig, da bedingten Zugriff aktiviert wurde <br/> |Einige Registerkarten möglicherweise nicht mehr auf dem Desktop Client geladen, da bedingten Zugriff auf den Mandanten aktiviert wurde. Die Registerkarten geladen werden, wenn die Web-Client verwenden. Einige Registerkarten, die möglicherweise betroffen sind: PowerBI, Formulare, VSTS, PowerApps und SharePoint-Liste.  <br/> |Um die betroffenen Registerkarten finden Sie unter müssen Sie mit der Windows-10-Konten Erweiterung installiert Teams in Edge, Internet Explorer oder Chrome verwenden. Einige Registerkarten hängen weiterhin Webauthentifizierung, die nicht in den Desktopclient funktioniert, wenn die Zertifizierungsstelle aktiviert ist. Wir arbeiten mit Partnern diese Szenarien zu ermöglichen; Bisher haben wir Planner, OneNote und Stream aktiviert. <br/> |4/5/18  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Die Liste der Arbeitsbereiche ist nicht alphabetisch sortiert.  <br/> |Wenn Benutzer eine Power BI-Registerkarte hinzufügen und dabei zwischen Arbeitsbereichen wechseln, wird eine nicht alphabetisch sortierte Liste der Arbeitsbereiche, zwischen denen sie wechseln können, angezeigt.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Die Scrollleiste wird beim Auswählen von Berichten nicht mehr angezeigt.  <br/> |Benutzer können beim Hinzufügen von Power BI-Berichten nicht durch eine Liste mit Berichten scrollen, die nicht auf den Bildschirm passt, ohne die Scrollleiste zu verlieren.  <br/> |Scrollen Sie mit der NACH-OBEN- und der NACH-UNTEN-TASTE durch die Liste.  <br/> |13.03.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Teams Planner Integration in Planner online <br/> |Buckets in Planner Aufgaben werden in Planner online-Erfahrung nicht angezeigt.  <br/> |Keine Problemumgehung. <br/> |28.02.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Registerkarte für SharePoint-Seite rendert leeren Bildschirm<br/> |SharePoint Online Vanity Domänen werden derzeit nicht unterstützt. Die Benutzeroberfläche ist ein leerer Bildschirm, wenn Attemting zum Hinzufügen einer SharePoint-Seite Registerkarte. <br/> |Keine Problemumgehung <br/> |8/20/18  <br/>|

## <a name="teams"></a>Microsoft Teams

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Überwachungsprotokolle können eine falsche Benutzername als Initiator melden, wenn eine Person aus einem Team entfernt wurde  <br/> |Teams Team ist eine moderne Gruppe in AAD. Wenn Sie ein Element über die Benutzeroberfläche des Teams Software, der Fluss weiß genau mit der der Benutzer die Änderung initiiert, und das Überwachungsprotokoll die korrekte Informationen widerspiegelt. Jedoch, wenn ein Benutzer fügt/Mitglied über AAD entfernt, wird die Änderung synchronisiert an die Teams Back-End-ohne Teams, die die Aktion initiiert hat. Microsoft-Teams, wählt den ersten Besitzer des Teams als der Initiator, der in das Überwachungsprotokoll sowie schließlich wiedergegeben wird.    <br/> |  <br/> |5/11/18  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Der Upload von Fotos in Microsoft Teams wird in OWA/Outlook nicht gemäß der Richtlinie blockiert.   <br/> | Microsoft Teams lässt zu, dass Benutzer Fotos direkt in Office 365 hochladen, obwohl Richtlinieneinstellungen vorhanden sind, die Fotouploads für OWA verhindern.   <br/> |<br/>  |16.10.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|In der Liste der öffentlichen Teams werden nicht alle Teams angezeigt.  <br/> |Die Liste der öffentlichen Teams basiert auf Microsoft Graph.  <br/> |Wenn Sie ein Team nicht sehen, suchen Sie es rechts oben im Suchfeld. Darüber hinaus sollten die Besitzer der Team Teamnamen für Kollegen kommunizieren, da viele Teams in den Suchergebnissen auftauchen konnte. <br/> | 21.07.2017  <br/>|

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Teamnamen, die Sonderzeichen enthalten können Fehler zur Erfüllung Creation erstellen.  <br/> |Benutzer erhalten die Meldung **Fehler** in Rot, beim Versuch, eine Besprechung für ein Team erstellen, Sonderzeichen im Namen hat.   <br/> |Umbenennen oder Neuerstellen Team mit einem Namen, die keiner "/".  <br/> |13.07.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Einen Teamnamen mit einer &amp; Symbol darin hebt Connector-Funktionalität  <br/> |Wenn ein Teamname mit dem Zeichen „&amp;“ erstellt wird, können Connectors im Team bzw. in der Gruppe nicht eingerichtet werden.  <br/> |Verwenden Sie in Teamnamen keine Sonderzeichen.  <br/> |21.06.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Maximale Anzahl von 2500 Mitgliedern pro Team  <br/> |Jedes Team in Microsoft Teams kann maximal 2500 Mitglieder enthalten.  <br/> |Keine Problemumgehung.  <br/> |13.03.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Beim Löschen eines Teams wird auch die zugeordnete Gruppe gelöscht.  <br/> |Benutzer wissen möglicherweise nicht, dass zusammen mit dem Team auch die zugrunde liegende Office 365-Gruppe gelöscht wird. Außerdem wird, wenn die zugrunde liegende Office 365-Gruppe gelöscht wird, auch das Team gelöscht.  <br/> |Diese Informationen werden in zusätzlichen Benutzermeldungen in Microsoft Teams angezeigt. Auf der Benutzeroberfläche von Office 365-Gruppen werden diese Informationen nicht angezeigt. Das Helpdesk kann eine gelöschte Group-Team wiederherstellen.  <br/> |13.03.2017  <br/> |

|**Titel des Problems**|**Verhalten/Symptom**|**Bekannte Problemumgehung**|**Datum der Erkennung**|
|:-----|:-----|:-----|:-----|
|Teams-desktop-app mit weißer Bildschirm  <br/> | <br/> |Versuchen Sie zu löschen oder die Grafiktreiber auf dem Computer oder Start Neuinstallieren Teams über eine Befehlszeile mit einer Disable GPU kennzeichnen:<ul><li>Öffnen Sie für Windows: Das Eingabeaufforderungsfenster, und geben Sie Folgendes ein:`cd %localappdata%\microsoft\teams\current run Teams.exe --disable-gpu`</li><li>Für Mac: Start Terminal und geben Sie Folgendes:`cd \Applications folder Microsoft\ Teams.app/Contents/MacOS/Teams --disable-gpu`</li></ul> <br/> |<br/> |

