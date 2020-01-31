---
title: Übersicht über Sicherheit und Compliance in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Eine Übersicht über die Sicherheits- und Compliance-Funktionen von Microsoft Teams, einschließlich Überwachung und Berichterstellung, Compliancesuche in Inhalten, eDiscovery und vielem mehr.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e0f6424770e2a0ccbe7367d2786949ef4ef2f6d
ms.sourcegitcommit: 5932ec62a42d7b392fa31c6a2a3462389ac24b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "41573641"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Übersicht über Sicherheit und Compliance in Microsoft Teams
======================================================

Microsoft Teams basiert auf der Office 365-Cloud auf Unternehmensniveau mit Hyperskalierung und bietet die erweiterten Sicherheits- und Compliance-Funktionen, die unsere Kunden erwarten.

Lassen Sie sich diese Microsoft Mechanics-Videos zur Sicherheit und Compliance nicht entgehen:
- [Microsoft Teams Essentials für IT: Sicherheit und Compliance](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Microsoft Teams-Steuerelemente für Sicherheit und Compliance](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

Microsoft Teams ist mit Stufe D konform. Dazu gehören die folgenden Standards: ISO 27001, ISO 27018, SSAE16 SOC 1 und SOC 2, HIPAA und EU-Standardvertragsklauseln (EU Model Clauses, EUMC). Microsoft klassifiziert innerhalb des Microsoft-Compliance-Frameworks Office 365-Anwendungen und -Dienste in vier Kategorien. Jede Kategorie wird durch bestimmte Compliance-Verpflichtungen definiert, die ein Office 365-Dienst oder ein zugehöriger Microsoft-Dienst erfüllen muss, um in dieser Kategorie geführt zu werden.

Dienste in den Compliance-Kategorien C und D, für die branchenführende Compliance-Verpflichtungen gelten, sind standardmäßig aktiviert. Dienste der Kategorien A und B verfügen über Steuermöglichkeiten, mit denen diese Dienste organisationsweit aktiviert oder deaktiviert werden können. Details hierzu finden Sie im Dokument zum [Compliance-Framework für Branchenstandards und -bestimmungen](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf). Microsoft Teams unterstützt außerdem Cloud Security Alliance-Compliance.

Microsoft Teams erzwingt außerdem teamweite und organisationsweite zweistufige Authentifizierung, einmaliges Anmelden über Active Directory und Verschlüsselung der übertragenen Daten sowie der ruhenden Daten. Dateien werden in SharePoint gespeichert und mit dem entsprechenden SharePoint-Mechanismus verschlüsselt. Notizen werden in OneNote gespeichert und mit dem entsprechenden OneNote-Mechanismus verschlüsselt. Die OneNote-Daten werden auf der SharePoint-Website des Teams gespeichert. Die Wiki-Registerkarte kann ebenfalls zum Erstellen von Notizen verwendet werden. Auch ihre Inhalte werden auf der SharePoint-Website des Teams gespeichert.

Außerdem haben wir Unterstützung für Überwachungsprotokollsuche, eDiscovery und gesetzliche Aufbewahrungspflicht für Kanäle, Chats und Dateien sowie mobile Anwendungsverwaltung mit Microsoft Intune hinzugefügt. Wechseln Sie zum Office 365 Security & Compliance Center, um diese Einstellungen zu verwalten. 

Weitere Informationen zu Office 365-Sicherheit und-Compliance finden Sie unter [Konfigurieren Ihres Office 365-Mandanten für erhöhte Sicherheit](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> Derzeit unterstützt [privater Kanal](private-channels.md) begrenzte Sicherheits-und Compliance-Funktionen. Die Unterstützung für den vollständigen Satz von Sicherheits-und Compliance-Features in privaten Kanälen wird in Kürze verfügbar sein.

## <a name="auditing-and-reporting"></a>Überwachung und Berichterstellung

Die Überwachungsprotokollsuche ist direkt in das Office 365 Security & Compliance Center integriert und macht Funktionen verfügbar, mit denen Sie Warnungen festlegen und/oder Berichte zu Überwachungsereignissen erstellen können, indem Sie Exporte von arbeitsauslastungsspezifischen oder generischen Ereignissätzen für unbegrenzte Überwachungszeiträume zur Verwendung durch Administratoren und zu Untersuchungszwecken verfügbar machen. Alle Überwachungsprotokolldaten stehen zum Einrichten von Warnungen sowie zum Filtern und Exportieren zur weiteren Analyse im Office 365 Security & Compliance Center zur Verfügung. Unter diesem [Link](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) finden Sie weitere Informationen zum Durchführen einer Überwachungsprotokollsuche für Microsoft Teams-Ereignisse im Office 365 Security & Compliance Center. 

## <a name="compliance-content-search"></a>Compliancesuche in Inhalten

Die Inhaltssuche kann dazu verwendet werden, mit umfangreichen Filterfunktionen nach allen Microsoft Teams-Daten zu suchen. Die Inhalte können zur Unterstützung von Compliance und Rechtsstreitigkeiten in einen speziellen Container exportiert werden. Dies kann mit oder ohne eDiscovery-Fall geschehen. Auf diese Weise können Complianceadministratoren Microsoft Teams-Daten für alle Benutzer sammeln, überprüfen und zur weiteren Verarbeitung exportieren. Unter diesem [Link](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) finden Sie weitere Informationen zum Durchführen einer Compliancesuche in Microsoft Teams-Inhalten im Office 365 Security & Compliance Center. 

Tipp: Wenn Sie ausschließlich nach Microsoft Teams-Inhalten (zum Beispiel nach Chat- und Kanalnachrichten, Besprechungen und Anrufen) filtern möchten, können Sie den Typ „Microsoft Teams“ verwenden.

## <a name="ediscovery"></a>eDiscovery

Bei eDiscovery handelt es sich um den elektronischen Aspekt beim Identifizieren, Sammeln und Erzeugen von elektronisch gespeicherten Informationen (ESI) als Reaktion auf die Aufforderung zur Vorlage dieser Informationen in einem Rechtsstreit oder einer Untersuchung. Zu den Funktionen gehören Fallmanagement, Erhaltung, Suche, Analyse und Export von Microsoft Teams-Daten. Dies schließt Zusammenfassungen für Chats, Nachrichten und Dateien sowie Besprechungen und Anrufe ein. Für Microsoft Teams-Besprechungen und -Anrufe wird eine Zusammenfassung der Ereignisse in Besprechungen und Anrufen erstellt und in der eDiscovery verfügbar gemacht. 

Weitere Details zum Ausführen einer eDiscovery im Security & Compliance Center und einer Compliancesuche in Microsoft Teams-Inhalten finden Sie unter den folgenden Links: 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[Inhaltssuche](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

Kunden können je nach ihren Anforderungen In-Situ-eDiscovery oder Advanced eDiscovery nutzen (https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4). In der folgenden Tabelle sind die Unterschiede zwischen den beiden Funktionen aufgeführt:


| |In-Situ-eDiscovery  |Advanced eDiscovery  |
|---------|---------|---------|
|Fallmanagement     |X        |X         |
|Access Control  |X         |X         |
|Suche in Inhalten     |X         | X        |
|Speicher   |X         | X        |
|Exportieren     |X         |X         |
|Erkennung von Duplikaten     |-         |X         |
|Relevanzsuche mit maschinellem Lernen    |-         |X         |
|Analyse unstrukturierter Daten      |-         |X         |


## <a name="legal-hold"></a>Aufbewahrung für juristische Zwecke

In einem Rechtsstreit müssen häufig alle Daten, die einem Benutzer (Depotbank) oder einem Team zugeordnet sind, als unveränderlich beibehalten werden, damit er als Beweis für den Fall verwendet werden kann. Dazu wird für einen Benutzer (Benutzerpostfach) oder ein Team die Aufbewahrung für juristische Zwecke festgelegt. Wenn für ein Team in Microsoft Teams ein In-Situ-Speicher (Teilmenge des Postfachs oder der Websitesammlung durch gezielte Abfragen oder Filtern der Inhalte) oder Beweissicherungsverfahren (gesamtes Postfach oder gesamte Websitesammlung) aktiviert wird, gilt dies für das Gruppenpostfach. Dadurch wird sichergestellt, dass auch wenn Endbenutzer im Gruppenpostfach erfasste Kanalnachrichten löschen oder bearbeiten, unveränderbare Kopien dieser Inhalte beibehalten werden und in einer eDiscovery-Suche verfügbar sind. Die Aufbewahrung für juristische Zwecke wird im Allgemeinen im Kontext eines eDiscovery-Falls angewendet. In [diesem Hilfeartikel](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) finden Sie weitere Informationen zur Erhaltung und Aufbewahrung im Office 365 Security & Compliance Center. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Informationsschutzarchitektur für Microsoft Teams 

Die folgende Abbildung zeigt den Ablauf der Erfassung von Microsoft Teams-Daten (Microsoft Teams-Dateien und -Nachrichten) in Exchange und SharePoint. 

![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

Die folgende Abbildung zeigt den Ablauf der Erfassung von Daten aus Microsoft Teams-Besprechungen und -Anrufen in Exchange.

![Diagramm des Workflows von Daten aus Microsoft Teams-Besprechungen und -Anrufen zu Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Beim Ermitteln von Microsoft Teams-Inhalten ist eine Verzögerung von bis zu 24 Stunden möglich.

<a name="licensing"></a>Lizenzierung
---------------

Die Funktionen für den Schutz von Informationen hängen von den Office 365-Abonnements und den zugehörigen eigenständigen Lizenzen ab.


| Funktion für den Schutz von Informationen | Office 365 Business Essentials | Office 365 Business Premium | Office 365 Enterprise E1 | Office 365 Enterprise E3/E4 | Office 365 Enterprise E5 |
|-----------------------------------|--------------------------------|-----------------------------|--------------------------|-----------------------------|--------------------------|
|              Archiv              |               -                |              -              |            -             |             Ja              |           Ja             |
|        Compliance-eDiscovery        |               -                |              -              |            -             |             Ja              |           Ja             |
|        Advanced eDiscovery        |               -                |              -              |            -             |              -              |           Ja            |
|            Gesetzliche Aufbewahrungspflicht             |               -                |              -              |            -             |             Ja              |           Ja             |
|     Compliancesuche in Inhalten     |               -                |             Ja              |           Ja             |             Ja              |           Ja            |
|      Überwachung und Berichterstellung       |              Ja               |             Ja              |           Ja             |             Ja              |           Ja            |
|       Bedingter Zugriff\*        |              Ja               |             Ja              |           Ja             |             Ja              |           Ja            |

> [!NOTE]
> \*Für bedingten Zugriff sind zusätzliche Lizenzen erforderlich.


| |  |  |
|---------|---------|---------|
|![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Entscheidungspunkt         |Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Compliance- und Sicherheitsanforderungen zu erfüllen?         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Nächste Schritte         |Überprüfen Sie die aktuellen Lizenzen Ihrer Organisation, und vergewissern Sie sich, dass diese alle geschäftlichen Anforderungen in Bezug auf Compliance und Sicherheit erfüllen.         |

Bevor Sie diese Funktionen aktivieren, müssen Sie sicherstellen, dass Sie auf das Security & Compliance Center im Microsoft 365 Admin Center zugreifen können. Mandantenadministratoren verfügen standardmäßig über Zugriff.

Inhaltssuche und eDiscovery müssen nicht im Security & Compliance Center aktiviert werden.

<a name="location-of-data-in-teams"></a>Speicherort von Daten in Microsoft Teams
-------------------------

Die Microsoft Teams-Daten befinden sich in der geografischen Region, die Ihrem Office 365-Mandanten zugeordnet ist. Derzeit unterstützt Microsoft Teams Australien, Kanada, Frankreich, Indien, Japan, Großbritannien, Südkorea, Südafrika, Nord- und Südamerika, APAC und EMEA. 

> [!IMPORTANT]
> Microsoft Teams bietet derzeit Datenspeicherung (nur für neue Mandanten) in Australien, Kanada, Frankreich, Indien, Japan, Großbritannien, Südkorea und Südafrika. Ein neuer Mandant wird definiert als ein Mandant, über den sich noch kein einziger Benutzer bei Microsoft Teams angemeldet hat. Bei bestehenden Mandanten aus Australien, Indien, Japan und Südkorea werden die entsprechenden Teams weiterhin in der Region APAC gespeichert. Die Daten bestehender Mandanten in Kanada weiterhin in Amerika gespeichert. Die Daten bestehender Mandanten in Frankreich, Großbritannien und Südafrika werden weiterhin in der Region EMEA gespeichert.

Weitere Informationen zur Datenspeicherung für Microsoft Teams in Südafrika finden Sie im Blogbeitrag "[Microsoft Teams launches South African Data Residency (Einführung der Datenspeicherung für Microsoft Teams in Südafrika)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)" von Varun Sagar.

In einem weiteren Blogbeitrag von Varun Sagar, "[Microsoft Teams launches South Korean Data Residency (Einführung der Datenspeicherung für Microsoft Teams in Südkorea)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)“, erfahren Sie Näheres zur Datenspeicherung für Microsoft Teams in Südkorea.

Weitere Informationen zur Einführung der Datenspeicherung für Microsoft Teams in Indien und im Vereinigten Königreich finden Sie in Ansuman Acharyas Blogbeitrag zur [Einführung der Datenspeicherung für Microsoft Teams in Indien und zu geplanten weiteren geografischen Regionen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827). 

Weitere Informationen zur Datenspeicherung für Microsoft Teams in Kanada finden Sie in Varun Sagars Blogbeitrag "[Microsoft Teams Launches Canada Data Residency, Australia and Japan coming soon (Einführung der Datenspeicherung für Microsoft Teams in Kanada; in Kürze auch in Australien und Japan)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)". 

Weitere Informationen zur Datenspeicherung für Microsoft Teams in Australien und Japan finden Sie in Varun Sagars Blogbeitrag "[Microsoft Teams Launches Australia and Japan Data Residency (Einführung der Datenspeicherung für Microsoft Teams in Australien und Japan)](https://go.microsoft.com/fwlink/?linkid=867773)". 

Weitere Informationen zur Datenspeicherung für Microsoft Teams in Frankreich finden Sie in Varun Sagars Blogbeitrag "[Microsoft Teams Launches France Data Residency (Einführung der Datenspeicherung für Microsoft Teams in Frankreich)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)".

Wenn Sie wissen möchten, in welcher Region sich die Daten für Ihren Mandanten befinden, wechseln Sie zu [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home)  > **Einstellungen** > **Organisationsprofil**. Scrollen Sie nach unten zu **Data location** (Datenspeicherort). 

![Screenshot der Tabelle „Data location“ (Datenspeicherort) einschließlich Microsoft Teams im Admin Center](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>Wie funktionieren Richtlinien für bedingten Zugriff in Verbindung mit Microsoft Teams?
-------------------------

Microsoft Teams nutzt in großem Umfang Exchange Online, SharePoint Online und Skype for Business Online für elementare Produktivitätsszenarien wie Besprechungen, Kalender, Interop-Chats und Dateifreigabe. Richtlinien für bedingten Zugriff, die für diese Cloud-Apps festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer direkt bei Microsoft Teams anmelden – unabhängig vom Client. 

Microsoft Teams wird separat als Cloud-App in Azure Active Directory-Richtlinien für bedingten Zugriff unterstützt. Richtlinien für bedingten Zugriff, die für die Microsoft Teams-Cloud-App festgelegt wurden, gelten auch für Microsoft Teams, wenn sich Benutzer anmelden. Ohne die richtigen Richtlinien für andere Apps wie Exchange Online und SharePoint Online jedoch können Benutzer möglicherweise dennoch direkt auf diese Ressourcen zugreifen. Weitere Informationen zum Einrichten einer Richtlinie für bedingten Zugriff im Azure-Portal finden Sie hier: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started). 

Microsoft Teams-Desktopclients für Windows und Mac unterstützen moderne Authentifizierung. Moderne Authentifizierung ermöglicht plattformübergreifend die Anmeldung auf der Grundlage von ADAL (Azure Active Directory Authentication Library, Active Directory-Authentifizierungsbibliothek) in Microsoft Office-Clientanwendungen.

Die Microsoft Teams-Desktopanwendung unterstützt AppLocker.  Weitere Informationen zu den Voraussetzungen für AppLocker finden Sie unter „Anforderungen für die Verwendung von AppLocker“ (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

<a name="privacy-in-teams"></a>Datenschutz in Microsoft Teams
--------------------------

Als Kunde von Office 365 sind Sie der Besitzer der Daten und verfügen auch über die vollständige Kontrolle. Microsoft verwendet Ihre Daten ausschließlich für die Bereitstellung des Diensts, den Sie abonniert haben. Als Dienstanbieter scannen wir nicht Ihre E-Mails, Dokumente oder Teams zu Werbezwecken oder nicht dienstbezogenen Zwecken. Microsoft hat keinen Zugriff auf hochgeladene Inhalte. Genau wie bei OneDrive for Business und SharePoint Online bleiben die Kundendaten im Mandanten.

Weitere Informationen zu den Themen „Vertrauensstellung“ und „Sicherheit“ finden Sie im [Microsoft Trust Center](https://microsoft.com/trustcenter). Microsoft Teams folgt den gleichen Leitlinien und Prinzipien wie das Microsoft Trust Center.

<a name="related-topics"></a>Verwandte Themen
----------------------
[ATP-sichere Links in Office 365](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)
