---
title: 'Patienten-App für Teams-Administratoren '
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
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Informationen zur Patienten-App für Teams-Administratoren
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b86c180bc809fa10b261738ae5b324737006f541
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772186"
---
# <a name="patients-app-overview"></a>Übersicht der Patienten-App

> [!NOTE]
> Die Patienten-App wurde im 30. Oktober, 2020, eingestellt und durch die [Listen-App](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams ersetzt. Mit Listen können Betreuerteams in Ihrer Gesundheitsorganisation patientenlisten für Szenarien erstellen, die von runden und interdisziplinären Teambesprechungen bis hin zur allgemeinen Patientenüberwachung reichen. Schauen Sie sich die Vorlage Patienten in Listen an, um zu beginnen. Weitere Informationen zum Verwalten der Listen-app in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md) .

Die patients-Anwendung ist eine Microsoft Teams Store-App, die für alle Teams-Benutzer verfügbar ist. Mit der App können Patienten Gesundheitsteams, bestehend aus klinischen Arbeitern (wie Krankenschwestern, Ärzten, Sozialarbeitern), Listen von Patienten für Szenarien, die von runden und interdisziplinären Teambesprechungen bis zur allgemeinen Patientenüberwachung reichen, kuratiert und überprüfen.

Die APP hat zwei Modi:

- Der EMR-verbundene Modus, der über FHIR eine Verbindung mit EMRs herstellt. Die EMR-App für den verbundenen Modus bleibt in der privaten Vorschau und interessierte Kunden oder Administratoren können den Zugriff auf die APP anfordern, indem Sie Microsoft eine e-Mail unter [teamsforhealthcare@Service.Microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) mit Informationen zu Ihrer Microsoft 365-Organisation ablegen.
- Der manuelle Modus, der es Gesundheitsteams ermöglicht, Patienteninformationen manuell hinzuzufügen/zu versorgen. Die Anwendung ist im Teams-App Store verfügbar, damit Endbenutzer Sie in der privaten Vorschau herunterladen können. Die APP kann mithilfe von [App-Setup Richtlinien](../../teams-app-setup-policies.md) in Teams auf bestimmte Benutzer Abschnitte beschränkt werden. Damit Sie auf die App zugreifen können, muss Ihr Mandant Teil des Technology Adoption Program (Tap) sein. Bitte senden Sie uns eine e-Mail an [teamsforhealthcare@Service.Microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) , um den Vorgang zum Anfordern des Zugriffs zu starten.

## <a name="usage-example"></a>Verwendungsbeispiel

Während der runden Sitzungen bei jeder Schicht in medizinischen Stationen versammeln sich Kliniker an der Krankenstation, um über die neuesten Updates über den Fortschritt bei Patienten in der Gemeinde zu diskutieren.  Sie betonen die wichtigsten wichtigen Metriken (nicht unbedingt medizinisch oder ausdrücklich auf die medizinischen Unterlagen der Patienten) und stellen sicher, dass sich der Patient auf dem richtigen Gleitweg befindet, um auf Grundlage seiner Diagnose zu entladen. Um diese Patienten umrunden zu können, richtet die Krankenschwester die Patienten-app in einem Team ein, in dem alle Ärzte hinzugefügt werden und Patienten zu einer Patientenliste hinzugefügt werden. Während der Runde greifen die Krankenschwestern und die anderen Betreuer für den Patienten auf die Microsoft Teams und die Patienten-App auf Ihren mobilen Geräten zu und aktualisieren relevante Patienteninformationen auf Ihrem Gerät, und alle anderen Personen im Gesundheitsteam können diese Updates und Notizen sehen und synchron bleiben. Zweimal am Tag, am Anfang und am Ende einer Schicht, haben Sie auch multidisziplinäre Teambesprechungen, um über die Patientenliste zu wechseln und die Patienten-APP zu verwenden, um sich selbst zu beerdigen und Informationen über jeden Patienten über die Patienten-App auf einem größeren Bildschirm zu teilen. Oft können sich bestimmte Kliniker auch Remote in diese Teams einwählen und dennoch Teil der Diskussion sein.

## <a name="configure-patients-app"></a>Konfigurieren der Patienten-App

Informationen dazu, wie Sie Ihre Umgebung auf die Verwendung der EMR-Modus-Patienten-App vorbereiten, finden Sie unter [integrieren elektronischer Gesundheitsdatensätze in Microsoft Teams](patients-app.md). Außerdem müssen Sie [in Microsoft Teams die Richtlinien für die APP-Einrichtung verwalten](../../teams-app-setup-policies.md) anzeigen, um die Patienten-App für Ihre Organisation zu aktivieren.

Informationen dazu, wie Ihre Endbenutzer auf die Patienten-App zugreifen und Sie in einem Team installieren können, das Sie besitzen oder verwalten, finden Sie unter [Erste Schritte mit Microsoft Teams-Patienten](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Häufig gestellte Fragen (FAQ)

**Wo werden die Daten der Patienten-APP gespeichert?**

Alle von Endbenutzern in die Patienten-App eingegebenen Daten, einschließlich des Spalten-/Feld Schemas, der tatsächlichen Daten, die in die Liste und Listenelemente eingegeben wurden (also Patienten), werden in der sicheren und kompatiblen Exchange Online-Infrastruktur gespeichert. Alle Daten werden in dem Gruppenpostfach gespeichert, das dem Team zugeordnet ist. Diese Architektur ermöglicht der Patienten-APP die einfache Erfüllung von Daten Wohnsitz, staatlicher Cloud-Unterstützung (in der Zukunft) sowie andere Compliance-und Informationsschutz Features wie eDiscovery-Unterstützung. Die Patienten-APP arbeitet in einem Teambereich. Sie müssen eine Instanz der APP pro Team installieren.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**Wo kann ich die Patienten-App abrufen?**

Wenn die patients-App für Ihre Organisation von Ihrem Administrator aktiviert ist, kann jeder Endbenutzer zum Teams-App-Store wechseln und die Patienten-APP einem Team hinzufügen, in dem Sie Mitglied sind. Weitere Informationen finden Sie unter [Verwalten von App-Setup Richtlinien in Microsoft Teams](../../teams-app-setup-policies.md).

**Kann ich in einem Team mehrere Instanzen der Patienten-APP haben, denn so funktioniert meine Station/Einheit?**

Derzeit können Sie nur eine Instanz der Patienten-App für ein bestimmtes Team und nur im Kanal "Allgemein" installieren. In der App können jedoch mehrere Listen erstellt werden, um Szenarien mit mehreren Kanälen oder Isolierung/Separation zu beheben. Standardmäßig können alle Mitglieder des Teams auf die Registerkarte "Patienten" im Kanal "Allgemein" zugreifen. 

**Kann ich alle Daten aus der Patienten-App exportieren?**
Nicht im Moment, aber diese Funktion wird in Kürze verfügbar sein. 

**Da diese APP Phi beherbergt, gibt es Audits, um unbefugten Zugriff zu verhindern oder Vorschriften zu erfüllen?**

Ja, das gibt es. Jede einzelne Benutzeroberflächen Aktion, die von einem Microsoft Teams-Benutzer in der Patienten-app ausgeführt wird, wird überwacht und im Security and Compliance Center zur Verfügung gestellt. Die Details werden in der [App Überwachungsprotokolle für Patienten](patients-audit.md)erläutert.

## <a name="related-topics"></a>Verwandte Themen

[Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams](patients-app.md)
