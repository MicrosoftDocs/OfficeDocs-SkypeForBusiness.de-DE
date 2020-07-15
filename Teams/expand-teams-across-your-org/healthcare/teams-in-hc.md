---
title: Erste Schritte mit Teams für Organisationen im Gesundheitswesen
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Informieren Sie sich über die Features für die Gesundheitsversorgung, die Betreuungs Koordination, sicheres Messaging, Telehealth, EPA-Integration und die Integration von Arbeitssystemen in erster Ordnung umfassen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d2a77e5e7e696e20efb13a5c805968fc3af3204
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138105"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Erste Schritte mit Teams für Organisationen im Gesundheitswesen

Microsoft Teams bietet eine Reihe von Funktionen, die für Krankenhäuser und andere Gesundheitsorganisationen nützlich sind. Die Features von Teams sind derzeit in der Entwicklung, um Krankenhäusern zu helfen:

- Pflege Koordination und Zusammenarbeit
- Sicheres Messaging
- Telehealth
- Integration elektronischer Gesundheitsakte (EPA) 
- Integration von Arbeitssystemen in ersterLinie 

Der Inhalt dieses Abschnitts basiert auf den grundlegenden Funktionen von Teams wie Besprechungen, anrufen und Nachrichten und geht davon aus, dass Sie bereits Teams in Ihrer Organisation bereitgestellt haben. Wenn Sie noch keine Teams ausgearbeitet haben, lesen Sie zunächst, [wie Sie Microsoft Teams Ausrollen](../../How-to-roll-out-teams.md).

## <a name="care-coordination---microsoft-teams-patients-app"></a>Pflege Koordination – Microsoft Teams patients-App

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams verfügt nun über eine speziell für Gesundheitsorganisationen spezifische Pflege Koordinierungs Lösung, die Ihnen hilft, die beste Patientenversorgung zu gewährleisten. Der Kern der Lösung zur Pflege Koordination, der Microsoft Teams patients-APP, ist eine APP des First-Party-Tabs, die mit einer schnellen Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/))-Schnittstelle integriert wird, die in das System der elektronischen Krankenakte (EPA) integriert ist, um wertvolle medizinische Informationen in Microsoft Teams zusammenzubringen, um die klinische Zusammenarbeit und Kommunikation zu ermöglichen.  

Die Lösung zur Pflege Koordination kann mit führenden unabhängigen Software Anbietern (Independent Software Vendors, ISVs) verbunden werden, die die Patienten-App mithilfe vorhandener Integritätsdaten Standards wie HL7v2 und FHIR mit ihren EPA-Systemen verbinden können. Microsoft-Partner mit den folgenden Branchenführern zur Einrichtung elektronischer Integritätsdaten Satz Integration in Teams:

- Datica (durch Ihr [CMI](https://datica.com/compliant-managed-integration/) -Angebot)
- Infor Kleeblatt (über die [Infor FHIR-Brücke](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (über den [R ^ FHIR-Server](https://www.redoxengine.com/fhir/))
- Dapasoft (über [FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

Ein EPA-Integrations-und Interop-Partner, der versucht, Microsoft Teams für eine Organisation des Gesundheitswesens zu implementieren, muss der Patienten-App eine sichere und authentifizierte Verbindung mit den EPA-Systemen des Gesundheits Dienstanbieters bereitstellen. Auf diese Weise kann der unidirektionale (schreibgeschützte) Fluss der relevanten Patientendaten in die Patienten-App übermittelt werden. Die patients-App versteht das FHIR-Format, sodass der Partner auch dafür verantwortlich ist, die aggregierten Daten aus verschiedenen anderen Formaten wie HL7v2 usw. in FHIR DSTU2 oder STU3 zu transformieren.

<br>

![Illustrations-Highlighting-Koordination und Zusammenarbeit](../../media/ehr-1.png)

<br>

Die patients-APP ist in elektronische Health Records (EPA)-Systeme integriert und ermöglicht es den Leistungserbringer, in Echtzeit innerhalb der sicheren Plattform von Teams über die Patientenversorgung zu kommunizieren. Die Patienten-APP ist die erste größere Investition in den Bereich der Pflege Koordination, die sich mit den folgenden Herausforderungen befassen soll:

- Geringe Effizienz in der Hand-offs und kritische Kommunikation durch die Patientenerfahrung
- Silo-Informationen, die Verwaltungslasten schaffen
- Unzufriedenheit von Klinikern mit komplexen und fragmentierten Tools für die Zusammenarbeit
- Ineffiziente in-Person-Pflege Koordination, die zu viel teure klinische Zeit verbrennen kann

Microsoft Teams ermöglicht es Ärzten, Klinikern, Krankenschwestern und anderen Mitarbeitern, effizient zusammenzuarbeiten, indem Sie:

- Teil eines einzelnen virtualisierten Teams, das an Office-Dokumenten arbeitet und zusammenarbeitet
- Beständige Unterhaltungen zu unterschiedlichen Patienten, die darauf achten müssen
- Verwenden von Kanälen mit Registerkarten als Möglichkeit, ihre Arbeit zu strukturieren, mit zusätzlicher Hilfe von Registerkarten, an die Sie Informationsquellen anheften können
- Verwenden von Kanal Besprechungen mit der Leistung von Teams für Audio-, Video-, Bildschirmfreigabe-, Aufzeichnung-und Transkriptions Funktionen zum Verwalten von täglichen Besprechungen
- Verwenden Sie die Patienten-APP, um eine Liste von Patienten mit hoher Gefährdung zu kuratiert, die überwacht werden müssen, und ziehen Sie Ihre neuesten Informationen aus dem EPA-System. Die Patienten-APP selbst fügt Microsoft Teams die folgenden Features hinzu:

    - Möglichkeit zum Erstellen mehrerer patientenlisten in einem einzigen Kanal
    - Möglichkeit zum Anzeigen und Sortieren von Informationen, die über Patienten über konfigurierbare Spalten angezeigt werden.
    - Möglichkeit zur automatischen Bereitstellung der APP über eine Teamvorlage
    - Verfügbar in der Teams-App für IOS und Android für Mobile First Healthcare-Mitarbeiter sowie Microsoft Teams Web-und Desktop-Client.
    - Unterstützung für FHIR-DSTU2-und STU3-Versionen mithilfe der Analyse der Konformitäts Anweisung.
    - Überwachungsprotokolle für alle Ansichts-und Suchaktionen auf der Benutzeroberfläche, um Phi pro HIPAA-Richtlinien zu schützen.

Die app "Patienten" basiert auf der Erweiterungs Plattform für Teams und nutzt das Registerkarten-Framework, um umfangreiche Patienten Inhalte in einem Kanal anzuzeigen. Weitere Informationen zu anderen Teams-apps und der Plattform selbst finden Sie unter [Apps für Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).  

> [!NOTE]
> Die Patienten-App befindet sich in der privaten Vorschau, und die FHIR-Schnittstelle befindet sich in Beta. Es wird davon ausgegangen, dass veröffentlichte Versionen nicht abwärtskompatibel sind.

![Screenshot der App "Patienten" auf Desktop-und mobilen Geräten](../../media/ehr-2.png)

Einzelheiten zur Implementierung finden Sie unter [integrieren elektronischer Gesundheitsdatensätze in Microsoft Teams](patients-app.md) .

## <a name="teams-templates"></a>Teams-Vorlagen

Neue Vorlagen für die Erstellung von Teams wurden entwickelt, um auf eine Krankenhauseinstellung anzuwenden, und weitere werden in Kürze erwartet. Auf diese Weise ist es einfacher, Teams zu erstellen, die von Mitarbeitern des Gesundheitswesens zur Koordinierung der Versorgung von Patienten in verschiedenen Abteilungen oder Stationen eingesetzt werden. Weitere Informationen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen für Organisationen im Gesundheitswesen](healthcare-templates.md). Teams können für interne Abteilungen wie Kardiologie oder für Pflegestationen gestartet werden, und weitere Vorlagen befinden sich in der Entwicklung.

## <a name="lists-app"></a>Listen-App

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Mithilfe der Listen-app in Teams können Teams Informationen nachvollziehen und die Arbeit organisieren. Die APP ist für alle Teams-Benutzer vorinstalliert und steht in allen Teams und Kanälen als Registerkarte zur Verfügung. Listen können von Grund auf neu erstellt werden, aus vordefinierten Vorlagen oder durch Importieren von Daten nach Excel.

Betreuerteams können die Vorlage "Patienten" verwenden, um loszulegen. Sie können Listen erstellen, um die Bedürfnisse und den Status von Patienten nachvollziehen zu können. Vorhandene Patientendaten in Excel-Tabellen können zum Erstellen einer Liste in Teams herangezogen werden. Diese Listen können für Szenarien wie Runden und Patientenüberwachung verwendet werden, um die Behandlung zu koordinieren.

Beispielsweise erstellt eine Kosten Krankenschwester eine Patientenliste in einem Team, das alle Betreuerteam Mitglieder umfasst. Während der Runden wird das Betreuerteam auf seinen mobilen Geräten auf Teams zugreifen und die Patienteninformationen in der Liste aktualisieren, die jeder im Team sehen kann, um synchron zu bleiben. Bei runden Sitzungen, in denen sich das Betreuerteam sammelt, um wichtige Integritäts Leistungsmetriken zu besprechen und zu bewerten, um sicherzustellen, dass ein Patient auf dem richtigen Gleitweg zur Entladung ist, kann er diese Informationen mithilfe von Teams auf einem größeren Bildschirm freigeben. Betreuerteam Mitglieder, die nicht auf der Website sind, können Remoteteil nehmen.

Nachfolgend finden Sie eine Beispielliste, die für die Patienten Rundung eingerichtet wurde.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Screenshot einer Beispielliste für die Patienten Rundung":::

Weitere Informationen finden Sie unter [Verwalten der Listen-App für Ihre Organisation in Teams](../../manage-lists-app.md).

## <a name="secure-messaging"></a>Sicheres Messaging

Secure Messaging unterstützt die Zusammenarbeit in Care Teams, einschließlich mehrerer neuer Funktionen:

- Ein Nachrichtenabsender kann eine besondere Priorität für seine Nachricht festzulegen, sodass der Empfänger wiederholt benachrichtigt wird, bis er die Nachricht gelesen hat.
- Ein Nachrichtenabsender kann eine Lesebestätigung anfordern, damit er benachrichtigt wird, wenn eine von Ihnen gesendete Nachricht vom Empfänger der Nachricht gelesen wurde.


Zusammen ermöglichen diese Features eine schnellere Berücksichtung dringender Nachrichten und die Gewissheit, dass die Nachricht empfangen und gelesen wurde. Neue Betreuerteams, die diese Funktionen verwenden, können für jeden Patienten erstellt werden. Diese Features sind Richtlinien basiert und können Einzelpersonen oder gesamten Teams zugewiesen werden.

Weitere Informationen finden Sie unter [Erste Schritte mit Richtlinien für sichere Nachrichten für Organisationen im Gesundheitswesen](messaging-policies-hc.md) .

Im Zusammenhang mit Secure Messaging können auch andere Mandanten von Organisationen des Gesundheitswesens verbunden werden, was eine umfassendere Kommunikation zwischen Mandanten ermöglicht. (Siehe [Verwalten des externen Zugriffs (Föderation) in Microsoft Teams](../../manage-external-access.md)).

## <a name="firstline-worker-integration"></a>Integration von First-Worker-Arbeitskräften

Microsoft Teams ist in die First-Worker-Anwendung integriert, mit der Sie die Funktionen von Shift-Mitarbeitern koordinieren können, und vieles mehr. Weitere Informationen finden Sie unter [Verwalten der Schicht-App für Ihre Organisation in Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).
