---
title: 'Die App "Patienten" für Microsoft Teams-Administratoren '
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
ms.openlocfilehash: 92bc7581610abf1dc8baab17d2e9d23abb6c6fd3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803503"
---
# <a name="patients-app-overview"></a>Übersicht über die Patienten-App

> [!NOTE]
> Mit Wirkung vom 30. Oktober 2020 wurde die App "Patienten" zurückgezogen und durch die App [Listen ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Microsoft Teams ersetzt. Die Daten der Patienten-App werden in dem Gruppenpostfach der Office 365-Gruppe gespeichert, das zum Team gehört. Alle der Patienten-App zugeordneten Daten bleiben in dieser Gruppe erhalten, auf sie kann aber nicht mehr über die Benutzeroberfläche zugegriffen werden. Benutzer können ihre Listen mithilfe der App [Listen](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) neu erstellen.
>
>Mit der Listen-App können Pflegeteams in Ihrer Organisation im Gesundheitswesen Patientenlisten für Szenarien erstellen, die von Visiten und interdisziplinären Teambesprechungen bis zur allgemeinen Patientenüberwachung reichen. Sehen Sie sich die Vorlage "Patienten" in der Listen-App an, um die ersten Schritte zu unternehmen. Weitere Informationen zum Verwalten der Listen-App in Ihrer Organisation finden Sie unter [Verwalten der Listen-App](../../manage-lists-app.md).

Bei der Anwendung "Patienten" handelt es sich um eine App aus dem Microsoft Teams Store, die für alle Benutzer von Teams zur Verfügung steht. Die App ermöglicht es Betreuungsteams aus Klinikmitarbeitern (z. B. Pflegekräfte, Ärzte, Sozialpädagogen), Patientenlisten für Szenarien zusammenzustellen und zu überprüfen, die von Gesprächsrunden und interdisziplinären Teambesprechungen bis hin zur allgemeinen Patientenüberwachung reichen.

Die App verfügt über zwei Modi:

- Der mit EMR verbundene Modus, der die Verbindung zu EMRs über FHIR herstellt. Die App mit EMR verbundenem Modus bleibt in der privaten Vorschau, und alle interessierten Kunden oder Administratoren können den Zugriff auf die App anfordern, indem sie Microsoft eine E-Mail mit Informationen zu ihrer Microsoft 365-Organisation an [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) senden.
- Der manuelle Modus, der es Betreuungsteams ermöglicht, Patienteninformationen manuell hinzuzufügen bzw. einzugeben. Die Anwendung kann von Endbenutzern im Microsoft Teams App Store in einer privaten Vorschau heruntergeladen werden. Die Nutzung der App kann in Microsoft Teams mithilfe von [Richtlinien für das App-Setup](../../teams-app-setup-policies.md) auf bestimmte Benutzer beschränkt werden. Um Zugriff auf die App zu erhalten, muss Ihr Mandant am Technology Adoption-Programm teilnehmen. Senden Sie uns bitte eine E-Mail an [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com), um den Zugriff zu beantragen.

## <a name="usage-example"></a>Verwendungsbeispiel

Zu jeder Schicht in Krankenstationen treffen sich Ärzte zu Besprechungen, um sich über die neuesten Informationen zu den Fortschritten der Patienten auf der Station auszutauschen.  Sie heben die wichtigsten kritischen Metriken (nicht notwendigerweise medizinische Metriken oder zu rein medizinischen Daten der Patienten) hervor und stellen sicher, dass der Patient auf dem richtigen Weg zur Entlassung ist. Für diese Gesprächsrunden richtet die leitende Pflegekraft die Patienten-App in einem Team ein, dem alle Ärzte hinzugefügt werden, während alle Patienten in eine Patientenliste eingetragen werden. Während der Gesprächsrunden greifen Pflegekräfte und andere Betreuer auf Microsoft Teams und die Patienten-App auf ihren Mobilgeräten zu und aktualisieren relevante Patienteninformationen. Alle anderen Mitglieder des Gesundheitsteams können dann diese Updates und Notizen sehen und bleiben auf diese Weise auf dem neuesten Stand. Zwei Mal am Tag, am Anfang und am Ende einer Schicht, finden zudem multidisziplinäre Teambesprechungen statt, bei denen die Patientenliste durchgegangen wird und die Patienten-App verwendet wird, um sich selbst zu informieren und Informationen zu jedem Patienten für alle auf einem großen Display darzustellen. Einige Ärzte werden sich oftmals auch remote in diese Microsoft Teams-Besprechungen einwählen und auf diese Weise an der Diskussion teilnehmen.

## <a name="configure-patients-app"></a>Konfigurieren der Patienten-App

Informationen dazu, wie Sie Ihre Umgebung für die Verwendung der Patienten-App im EMR-Modus vorbereiten, finden Sie unter [Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams](patients-app.md). Lesen Sie auch [Verwalten von Richtlinien für das App-Setup in Microsoft Teams](../../teams-app-setup-policies.md), um die Patienten-App für Ihre Organisation zu aktivieren.

Informationen dazu, wie Ihre Endbenutzer auf die Patienten-App zugreifen und sie in einem Team installieren können, dessen Besitzer sie sind oder das sie verwalten, finden Sie unter [Erste Schritte mit "Patienten" in Microsoft Teams](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Häufig gestellte Fragen (FAQ)

**Wo werden die Daten der Patienten-App gespeichert?**

Alle von Endbenutzern in die Patienten-App eingegebenen Daten, einschließlich des Spalten-/Feldschemas, der tatsächlichen Daten, die in die Liste eingegeben wurden sowie die Listenelemente (d. h. Patienten), werden in der sicheren und Compliance-konformen Exchange Online-Infrastruktur gespeichert. Alle Daten werden in dem Gruppenpostfach gespeichert, das dem Team zugeordnet ist. Diese Architektur ermöglicht es der Patienten-App, Datenresidenz, Support für die Government Cloud (in Zukunft) und weitere Compliance-/Informationsschutzfunktionen wie eDiscovery-Support auf einfache Weise zu gewährleisten. Die Patienten-App wird auf Teamebene verwendet. Sie müssen eine Instanz der App pro Team installieren.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**Wo kann ich die Patienten-App erwerben?**

Wenn der Administrator die Patienten-App für seine Organisation aktiviert hat, kann jeder Endbenutzer zum Microsoft Teams App Store gehen und die App einem Team hinzufügen, dem er angehört. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für das App-Setup in Microsoft Teams](../../teams-app-setup-policies.md).

**Kann ich mehrere Instanzen der Patienten-App in einem Team haben, weil meine Abteilung/Station so funktioniert?**

Derzeit können Sie nur eine Instanz der Patienten-App pro Team und nur im allgemeinen Kanal installieren. Innerhalb der App können jedoch mehrere Listen erstellt werden, um Szenarien mit mehreren Kanälen oder Isolation/Trennung zu berücksichtigen. Standardmäßig haben alle Mitglieder des Teams Zugriff auf die Registerkarte "Patienten" im Kanal "Allgemein". 

**Kann ich alle Daten aus der Patienten-App exportieren?**
Derzeit nicht, aber diese Funktion wird in Kürze verfügbar sein. 

**Da diese App geschützte Gesundheitsinformationen enthalten kann, gibt es eine Überwachung, um unbefugten Zugriff zu verhindern oder die Einhaltung von Vorschriften zu gewährleisten?**

Ja. Jede einzelne Benutzeroberflächenaktion, die ein Microsoft Teams-Benutzer in der Patienten-App ausführt, wird überwacht und ist im Sicherheits- und Compliance Center verfügbar. Die Details hierzu finden Sie unter [Überwachungsprotokolle für die Patienten-App](patients-audit.md).

## <a name="related-topics"></a>Verwandte Themen

[Integration von elektronischen Datensätzen aus dem Gesundheitswesen in Microsoft Teams](patients-app.md)
