---
title: Verwalten der Genehmigungs-App in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: farhazk
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Erfahren Sie, wie Sie die Genehmigungs-App für Ihre Organisation in Microsoft Teams verwalten.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ed0eaeaeb7deb98de09f8c2eb06316985e7176b
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397046"
---
# <a name="manage-the-approvals-app-in-microsoft-teams"></a>Verwalten der Genehmigungs-App in Microsoft Teams

Die App "Genehmigungen" steht als persönliche App für alle Benutzer von Microsoft Teams zur Verfügung.
Die App "Genehmigungen" bietet eine einfache Möglichkeit, um in Microsoft Teams Überwachung, Compliance, Verantwortlichkeit und Workflows sowohl in strukturierte als auch unstrukturierte Genehmigungen zu bringen.

 ![zeigt die Genehmigungs-App an.](media/approvals-selection.png)

Benutzer können die App "Genehmigungen" an der Menüleiste anheften.

 ![zeigt die Genehmigungs-App mit der Option "Anheften" an.](media/approvalApp-pin.png)

Die erste Genehmigung, die von der Genehmigungs-App erstellt wurde, löst die Bereitstellung der Genehmigungslösung in der Microsoft Dataverse-Standardumgebung aus. Von der Genehmigungs-App erstellte Genehmigungen werden in der Microsoft Dataverse-Standardumgebung gespeichert.

In diesem Artikel werden die Anforderungen und Rollen für die App "Genehmigungen" beschrieben.

> [!NOTE]
> Dieses Feature wurde noch nicht für Benutzer von Government Community Cloud High (GCCH) und Department of Defense (DOD) veröffentlicht.

## <a name="required-permissions-and-licenses"></a>Erforderliche Berechtigungen und Lizenzen

Zum Bereitstellen der Genehmigungs-App benötigen Sie die Berechtigung für die folgenden Elemente:

- Berechtigungen zum Erstellen einer Microsoft Dataverse-Datenbank.

- Ein Konto auf [powerautomate.microsoft.com](https://powerautomate.microsoft.com/)

- Administratorrolle in der Zielumgebung.

- Lizenz für [Power Automate](/power-automate/get-started-approvals), Office 365 oder Dynamics 365.

- Eine Lizenz für Microsoft Forms ist erforderlich, damit Benutzer neue Genehmigungsvorlagen einrichten können.

Um die Genehmigungs-App zu verwenden, benötigen Sie eine Lizenz für Power Automate, und Ihr Konto wird automatisch der Rolle "Genehmigungsbenutzer" in der Zielumgebung bei Ihrer ersten Genehmigungszuweisung hinzugefügt.

## <a name="storage-with-microsoft-dataverse"></a>Speicher mit Microsoft Dataverse

Das Common Data Model (CDM) ist die freigegebene Datensprache, die von Geschäfts- und Analyseanwendungen in Microsoft Dataverse verwendet wird. Es besteht aus einer Reihe standardisierter, erweiterbarer Datenschemas, die von Microsoft und unseren Partnern veröffentlicht werden und die Konsistenz von Daten und deren Bedeutung über Anwendungen und Geschäftsprozesse hinweg ermöglichen. Weitere Informationen zum [Allgemeinen Datenmodell der Microsoft Power Platform](/power-automate/get-started-approvals).

Weitere Informationen zum [Genehmigungsworkflow](/power-automate/modern-approvals).

Genehmigungen, die anhand einer Vorlage erstellt werden, speichern weiterhin Daten in Microsoft Dataverse, z. B. Titel, Details, Vorlagen-ID und vieles mehr. Antworten, die auf der Genehmigungsanforderung übermittelt werden, werden in Forms gespeichert. Weitere Informationen zur [Datenspeicherung für Microsoft Forms](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe).

>[!Note]
>Wenn Sie die Formularvorlage auf der Microsoft Forms Website löschen, wird ihre Genehmigungsvorlage unterbrochen, und benutzer können die Anforderung nicht starten. Benutzer erhalten die Fehlermeldung "CDB TableNotFound", wenn sie versuchen, eine Genehmigungsvorlage zu öffnen, die auf Microsoft Forms gelöscht wird.

Vorlagen auf Organisationsebene teilen sich die gleiche Lebensdauer des Mandanten und vorlagen mit Teambereich teilen sich die gleiche Lebensdauer des Teams. Daher werden beim endgültigen Löschen des Teams die zugehörigen Vorlagen gelöscht.

## <a name="approvals-teams-app-permissions"></a>Berechtigungen für die Microsoft Teams-App "Genehmigungen"

Über die Microsoft Teams-App "Genehmigungen" können Sie auf die folgenden Features zugreifen:

- Empfangen von Nachrichten und Daten, die Sie bereitstellen.

- Versand von Nachrichten und Benachrichtigungen an Sie.

- Rendern persönlicher Apps und Dialogfelder ohne eine von Microsoft Teams bereitgestellte Kopfzeile.

- Zugriff auf Ihre Profilinformationen wie Name, E-Mail-Adresse, Firmenname und bevorzugte Sprache.

- Empfangen von Nachrichten und Daten, die Teammitglieder in einem Kanal bereitstellen.

- Senden von Nachrichten und Benachrichtigungen in einem Kanal.

- Zugriff auf die Informationen Ihres Teams:
  - Teamname
  - Kanalliste
  - Liste (Namen und E-Mail-Adressen der Teammitglieder)

- Verwenden der Teaminformationen zur Kontaktaufnahme.

Berechtigungen für Genehmigungsvorlagen

- Alle Teambesitzer können eine Genehmigungsvorlage für Teams erstellen, die sie besitzen.

- Wenn ein Administrator zum ersten Mal eine Vorlage für die gesamte Organisation erstellt, erstellt er automatisch eine neue Azure Active Directory (AAD)-Gruppe für alle Administratoren des Mandanten, einschließlich der globalen und Teams-Dienstadministratoren. Diese Administratoren werden als Besitzer der Gruppe hinzugefügt, sodass sie Organisationsvorlagen gemeinsam verwalten können. Administratoren, die neu in der Organisation sind, nachdem das Team erstellt wurde, müssen manuell als Gruppenbesitzer hinzugefügt werden, damit sie über die gleichen Berechtigungen zum Verwalten organisationsweiter Vorlagen verfügen.

> [!Note]
> Wenn ein Administrator die Gruppe löscht, haben Sie einen Monat Zeit, um sie im Azure Active Directory (AAD)-Portal wiederherzustellen, um alle zugehörigen Daten wiederherzustellen. Nach einem Monat oder wenn der Administrator diese Gruppe im Papierkorb löscht, gehen alle zugehörigen Daten verloren.

## <a name="disable-the-approvals-app"></a>Deaktivieren der App "Genehmigungen"

Die App "Genehmigungen" ist standardmäßig verfügbar. Sie können die App im Microsoft Teams Admin Center deaktivieren.

  1. Melden Sie sich beim Microsoft Teams Admin Center an.

  2. Wechseln Sie **Teams-Apps** > **Apps verwalten**.

  3. Suchen Sie nach der App "Genehmigungen".

     ![zeigt die Admin Center-Navigation mit hervorgehobener Option "Teams-Apps > Apps verwalten" an.](media/manage-approval-apps.png)

  4. Wählen Sie **"Genehmigungen" aus**.

  5. Deaktivieren Sie die App für Ihre Organisation mithilfe des Schalters.

     :::image type="content" alt-text="zeigt die Details für die Genehmigungs-App an." source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="pin-approvals-to-teams"></a>Anheften von Genehmigungen an Teams

### <a name="use-the-tailored-frontline-app-experience-to-pin-approvals-and-other-apps-to-teams"></a>Verwenden sie die maßgeschneiderte App-Erfahrung in Service und Produktion, um Genehmigungen und andere Apps an Teams anzuheften.

Die maßgeschneiderte Frontline-App-Erfahrung in Teams heftet die relevantesten Apps in Teams für Benutzer an, die über eine [F-Lizenz](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) verfügen. Angeheftete Apps umfassen Genehmigungen, Walkie-Talkie, Aufgaben und Schichten. Standardmäßig ist dieses Feature aktiviert, sodass Ihre Mitarbeiter in Service und Produktion eine out-of-the-box-Erfahrung erhalten, die auf ihre Anforderungen zugeschnitten ist.

Die Apps sind an die App-Leiste angeheftet – die Leiste auf der Seite des Teams-Desktopclients und am unteren Rand der mobilen Teams-Clients, auf die Benutzer schnell und einfach zugreifen können.

Weitere Informationen, einschließlich der Funktionsweise der Umgebung mit von Ihnen festgelegten App-Richtlinien, finden Sie unter ["Anpassen von Teams-Apps für Mitarbeiter in Service und Produktion](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)".

### <a name="use-an-app-setup-policy-to-pin-approvals-to-teams"></a>Verwenden einer App-Setuprichtlinie zum Anheften von Genehmigungen an Teams

Mit App-Setuprichtlinien können Sie Teams so anpassen, dass Apps angeheftet werden, die für Ihre Benutzer in Ihren Benutzern am wichtigsten sind.

Um die Genehmigungs-App für Ihre Benutzer anzuheften, können Sie die globale Richtlinie (organisationsweite Standardrichtlinie) bearbeiten oder eine benutzerdefinierte App-Setuprichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter [Verwalten von App-Einrichtungsrichtlinien in Microsoft Teams](teams-app-setup-policies.md).

## <a name="retention-policy"></a>Aufbewahrungsrichtlinie

Genehmigungen, die mit der Genehmigungs-App erstellt wurden, werden in der Microsoft Dataverse-Standardumgebung gespeichert, die derzeit keine Sicherungen unterstützt. Erfahren Sie mehr über das [Sichern und Wiederherstellen von Umgebungen – Power Platform \| Microsoft-Dokumentation](/power-platform/admin/backup-restore-environments).

In Formularen gespeicherte Daten werden erst gelöscht, wenn die Teambesitzer sie von der Registerkarte **"Gelöschte Formulare**" in der Microsoft Forms Web-App bereinigen.

## <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Derzeit unterstützt die Genehmigungs-App in Teams keine Richtlinien für bedingten Zugriff, die für Microsoft Teams festgelegt sind.

## <a name="data-limitations"></a>Dateneinschränkungen

Jedes Team kann maximal 400 Genehmigungsvorlagen enthalten, und jede Vorlage kann maximal 50.000 Anforderungen basierend auf der aktuellen Funktion in Microsoft Forms sammeln.

## <a name="auditing"></a>Überwachung

Die App "Genehmigungen" protokolliert Überwachungsereignisse im Microsoft 365 Security & Compliance Center. Sie können dieses Überwachungsprotokoll einsehen.

1. Wechseln Sie zum Microsoft 365 Compliance Center.

2. Wählen Sie den Abschnitt **Überwachung** aus.

3. Suchen Sie nach Aktivitäten unter **Aktivitäten in Microsoft Teams "Genehmigungen"**.

Sie können nach den folgenden Aktivitäten suchen:

- Erstellen einer neuen Genehmigungsanforderung

- Anzeigen von Details zu Genehmigungsanforderungen

- Genehmigte Genehmigungsanforderung

- Abgelehnte Genehmigungsanforderung

- Stornierte Genehmigungsanforderung

- Freigegebene Genehmigungsanforderung

- An Genehmigungsanforderung angefügte Datei

- Neu zugewiesene Genehmigungsanforderung

- Zu Genehmigungsanforderung hinzugefügte digitale Signatur

- E-Signatur-Anforderungsdetails angezeigt

- Überprüfte E-Signaturanforderung

- E-Signaturanforderung abgebrochen

- Erstellen einer neuen Vorlage

- Bearbeiten einer vorhandenen Vorlage

- Aktivieren/Deaktivieren einer Vorlage

- Angezeigte Vorlage

Für den Zugriff auf weitere Überwachungsgenehmigungen in Power Automate aktivieren und konfigurieren Sie die Überwachung in der Standardumgebung für die primären Genehmigungsentitäten Genehmigung, Genehmigungsanforderung und Genehmigungsantwort. Erstellen, Aktualisieren und Löschen sind überwachbare Ereignisse für Genehmigungseinträge. Weitere Informationen zur [Überwachung von Daten und Benutzeraktivitäten für Sicherheit und Compliance – Power Platform\| Microsoft-Dokumentation](/power-platform/admin/audit-data-user-activity).

Die Überwachung kann im [Microsoft 365 Security & Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US) weiter angepasst werden.

1. Um die vorkonfigurierten Berichte zu verwenden, melden Sie sich bei Microsoft 365 Security and Compliance an.

2. Wählen Sie **Suche und Untersuchung** aus.

3. Suchen Sie das Überwachungsprotokoll, und wählen Sie die Registerkarte **Dynamics 365-Aktivitäten** aus.

Weitere Informationen über die [Microsoft Dataverse- und modellgesteuerte App-Aktivitätsprotokollierung – Power Platform](/power-platform/admin/enable-use-comprehensive-auditing).

## <a name="security"></a>Sicherheit

Über die Microsoft Teams-App "Genehmigungen" können Benutzer neue Genehmigungen erstellen und solche anzeigen, die sie gesendet und erhalten haben. Die Benutzer haben keinen Zugriff auf Genehmigungen, die von anderen erstellt wurden, es sei denn, sie sind eine antwortende oder anzeigende Person der Anforderung.

> [!Note]
> Ein Benutzer erhält eine Viewerrolle einer Anforderung, wenn er Teil des Chats oder Kanals ist, in dem die Genehmigung erstellt wurde. Er hat nicht die Möglichkeit, Maßnahmen für die Anforderung zu ergreifen, wenn ihm diese Rolle beim Erstellen der Genehmigung nicht erteilt wurde.

## <a name="approvals-e-signature-integration"></a>E-Signatur-Integration von Genehmigungen

Um das E-Signatur-Feature der Genehmigungs-App zu verwenden, benötigen Sie eine Lizenz für den bestimmten E-Signaturanbieter, den Sie verwenden möchten. Um eine Lizenz für Ihre Organisation zu erhalten, müssen Sie zur Website des Anbieters wechseln.

### <a name="enable-or-disable-e-signature-providers"></a>Aktivieren oder Deaktivieren von E-Signaturanbietern

Sie können das Teams Admin Center verwenden, um zu steuern, welche E-Signatur-Anbieter von Drittanbietern Ihren Benutzern in der Genehmigungs-App zur Verfügung stehen. Standardmäßig sind E-Signatur-Anbieter in der Genehmigungs-App aktiviert. Wenn Sie einen E-Signaturanbieter deaktivieren, haben Ihre Benutzer beim Erstellen von Genehmigungen keinen Zugriff auf diesen Anbieter. Ihre Benutzer können auch keine E-Signaturanforderungen anzeigen, die mit diesem Anbieter erstellt wurden.

1. Wechseln Sie im linken Bereich des Teams Admin Centers zu **"Teams-Apps** > **verwalten"**.
2. Suchen Sie nach der Genehmigungs-App, und wählen Sie sie aus.
3. Wechseln Sie zur Registerkarte **"Einstellungen** ", und führen Sie dann eine oder mehrere der folgenden Aktionen aus:

    - Um Adobe Sign zu aktivieren oder zu deaktivieren, schalten Sie den Umschalter auf **"Ein** " oder " **Aus**".
    - Um DocuSign zu aktivieren oder zu deaktivieren, schalten Sie den Umschalter auf **"Ein** " oder " **Aus**".
4. Wählen Sie **"Absenden" aus**.

E-Signaturgenehmigungen, die über die Genehmigungs-App erstellt wurden, werden in der Cloudumgebung des ausgewählten Anbieters gespeichert. Um Daten zu E-Signaturen zu exportieren, müssen Sie zur Website des Anbieters wechseln. Weitere Informationen zum Speichern, Exportieren und Aufbewahren von E-Signatur-Vereinbarungen finden Sie in der Dokumentation des Anbieters.
