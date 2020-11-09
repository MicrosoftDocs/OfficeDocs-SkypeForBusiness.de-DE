---
title: Microsoft Teams-Richtlinien und Richtlinienpakete für EDU-Administratoren
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Priority
search.appverid: MET150
description: Erfahren Sie mehr über Richtlinien in einer Bildungs- oder EDU-Umgebung sowie über die Verwendung und Verwaltung von Richtlinienpaketen in Microsoft Teams.
ms.openlocfilehash: f580d8c41fe629a1c705f650a2aef84302128c20
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908614"
---
# <a name="teams-policies-and-policy-packages-for-education"></a>Teams-Richtlinien und -Richtlinienpakete für Bildungseinrichtungen

> [!NOTE]
> Wenn Sie generell mehr über Richtlinien in Microsoft Teams erfahren möchten, lesen Sie [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md).

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a>Administratoren: erste Schritte mit der Microsoft Teams-Richtlinienverwaltung

Mit Microsoft Teams können Benutzer unter anderem an Onlinebesprechungen oder Liveveranstaltungen teilnehmen, chatten, Anrufe tätigen und Apps nutzen. Die Festlegung des richtigen Administrators für Microsoft Teams ist ein entscheidender Schritt, um dafür zu sorgen, dass Teams eine sichere Lernumgebung für die Lernenden darstellt. Als Administrator können Sie Richtlinien verwenden, um zu steuern, welche Teams-Funktionen für die Benutzer in Ihrem Bildungsinstitut verfügbar sind.  In den meisten Fällen müssen die Richtlinien sowohl für Lernende als auch für Lehrkräfte angepasst werden, damit die Umgebung sicher bleibt.  

Nachstehend finden Sie eine Liste der Hauptrichtlinienbereiche, die in Microsoft Teams verfügbar sind. Wenn Sie mehr über die Richtlinien in den einzelnen Bereichen und die von ihnen gesteuerten Funktionen wissen möchten, verwenden Sie die folgenden Links:

- [Besprechungen](meeting-policies-in-teams.md)
- [Liveereignisse](teams-live-events/configure-teams-live-events.md)
- [Anrufe](teams-calling-policy.md) 
- [Nachrichten](messaging-policies-in-teams.md)
- [Microsoft Teams](teams-policies.md)
- [App-Berechtigungen](teams-app-permission-policies.md)

:::image type="content" source="media/edu-admin-center-users.png" alt-text="Screenshot eines Benutzers mit angewendeten Richtlinien":::

Sie können alle Teams-Richtlinien im [Microsoft Teams Admin Center](https://admin.teams.microsoft.com) verwalten, indem Sie sich mit Ihren Administratoranmeldeinformationen anmelden.

### <a name="where-to-find-microsoft-teams-policies"></a>Wo Sie die Microsoft Teams-Richtlinien finden

Sobald Sie sich beim Teams Admin Center angemeldet haben, können Sie zu den Richtlinieneinstellungen für alle Bereiche von Teams wechseln, die Sie verwalten müssen. Klicken Sie dazu in der linken Navigationsleiste des Teams Admin Center auf die Richtlinienoption. Wir haben einen Screenshot des Speicherortes der Messagingrichtlinien hinzugefügt.

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Speicherort der Messaging-Richtlinie im Admin Center von Teams.":::

### <a name="how-to-create-and-update-a-policy-definition"></a>Erstellen und Aktualisieren einer Richtliniendefinition

Bevor Sie Ihren Benutzern Richtlinien zuweisen, müssen Sie zuerst Ihre Richtliniendefinitionen für jeden Fähigkeitenbereich von Teams hinzufügen und erstellen.

> [!NOTE]
> Wir empfehlen, dass Sie für Ihre Schüler/Studenten und Lehrkräfte unterschiedliche Richtliniendefinitionen festlegen.

Standardmäßig wird jedem neuen Benutzer (Kursteilnehmer oder Lehrkraft) die globale Richtlinie (standardmäßig) für jeden Fähigkeitenbereich zugewiesen. Wir empfehlen, dass Sie für Ihre strengsten Richtliniendefinitionen den globalen (organisationsweiter Standard) verwenden. In den meisten Fällen wird sich dieser strengere Richtliniensatz für die Lernenden besser eignen. Wenn Sie Ihre globale (organisationsweiter Standard) Richtliniendefinition auf diese Weise verwenden, stellen Sie sicher, dass neue Benutzer die strengsten Einschränkungen haben, wenn sie zu Ihrem Mandanten hinzugefügt werden. Wir empfehlen Ihnen, sich an diese Anleitung zu halten und die folgenden Schritte zu befolgen:

1. Erstellen Sie eine benutzerdefinierte Richtliniendefinition für jeden Teams-Fähigkeitenbereich mit Richtlinienwerten, die den Bedürfnissen Ihrer Lehrkräfte entsprechen (ohne diese Definition haben Lehrkräfte denselben eingeschränkten Zugriff wie Ihre Lernenden, wie er in der globalen (organisationsweiter Standard) Richtliniendefinition definiert ist).

1. Weisen Sie diese neuen benutzerdefinierten Richtliniendefinitionen Ihren Lehrkräften zu.

1. Bearbeiten Sie die globalen (organisationsweiter Standard) Richtliniendefinitionen für jeden Fähigkeitenbereich mit Werten, die für Ihre Lernenden geeignet sind.

1. Die globalen (organisationsweiter Standard) Richtliniendefinitionen werden auf Ihre Lernenden angewandt, solange ihnen keine anderen Richtliniendefinitionen zugewiesen sind.


Um Richtliniendefinitionen zu erstellen oder zu bearbeiten, wechseln Sie zum Richtlinien-Fähigkeitenbereich, in dem Sie arbeiten möchten (z. B. Nachrichtenrichtlinien). Wählen Sie **Hinzufügen** aus, um eine neue benutzerdefinierte Richtliniendefinition zu erstellen. Wählen Sie **Bearbeiten** aus, um eine bestehende Richtliniendefinition zu ändern.

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="Nahaufnahme des Abschnittes mit den Messagingrichtlinien und der Schaltfläche „Hinzufügen“.":::

Unabhängig davon, ob Sie eine Richtliniendefinition hinzufügen oder bearbeiten, werden Sie zu einer Übersicht geführt, in der alle Richtlinienoptionen aufgelistet sind, die mit diesem Richtlinienbereich zu tun haben. Verwenden Sie diese Liste, um auszuwählen, welche Werte Sie in Ihrer Richtliniendefinition festlegen möchten.

![Eine Seite mit Ihren Richtlinienoptionen im von Ihnen ausgewählten Richtlinienbereich.](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> Vergessen Sie nicht, **Speichern** auszuwählen, bevor Sie die Seite verlassen.

### <a name="assigning-policy-definitions"></a>Zuweisen von Richtliniendefinitionen 
Es gibt mehrere Methoden, mit denen Sie Ihren Benutzern Richtliniendefinitionen zuweisen können. Jede Methode hat ihre eigenen Vor- und Nachteile, die je nach den spezifischen Anforderungen Ihrer Institution unterschiedlich sein können.  

In den meisten Fällen wird empfohlen, Ihren Benutzern Richtlinien mit Hilfe von Gruppenrichtlinienzuweisungen zuzuweisen. Diese Methode ermöglicht eine schnellere und nahtlosere Richtlinienanwendung.  Wenn ein Benutzer einer Gruppe hinzugefügt wird, der eine Richtliniendefinition zugewiesen ist, erbt der neue Benutzer automatisch die Richtlinien der Gruppe.  Auf diese Weise lässt sich die Richtlinie einfacher verwalten, wenn eine große Anzahl von Benutzern zur Umgebung hinzugefügt oder daraus entfernt wird, z. B. am Anfang und Ende eines Schulhalbjahrs.  

Für große Organisationen empfiehlt sich außerdem die Stapelverarbeitungszuweisung von Richtlinien, die auf Fälle zugeschnitten ist, in denen Sie großen Gruppen von Benutzern Richtlinien zuweisen müssen. Weitere Informationen zu diesen Anwendungsmethoden finden Sie unter [Zuweisen von Richtlinien zu großen Gruppen von Benutzern in Ihrer Schule](batch-group-policy-assignment-edu.md).

Wenn Sie eine kleinere Einrichtung sind oder die Richtlinieneinstellungen eines einzelnen Schülers oder einer einzelnen Lehrkraft aktualisieren müssen, befolgen Sie die folgenden Anweisungen.  

> [!IMPORTANT]
> Richtlinienzuweisungen, die auf der Ebene einzelner Benutzer festgelegt werden, setzen alle dem Benutzer zugewiesenen Gruppenrichtlinien außer Kraft. Stellen Sie sicher, dass Sie nur einzelne Richtlinienzuweisungen verwenden, wenn Sie die Gruppenrichtlinieneinstellungen außer Kraft setzen möchten. 

#### <a name="how-to-assign-a-policy-definition-to-a-user"></a>So weisen Sie einem Benutzer eine Richtliniendefinition zu

> [!NOTE]
> Beim Zuweisen einer Richtliniendefinition kann es eine Weile dauern, bis diese an alle Benutzer und Clients weitergegeben wird. Möglicherweise möchten Sie dies tun, wenn die Benutzerkonten erstmalig in Azure/M365 erstellt werden und immer wenn ein neuer Schüler der Bildungseinrichtung beitritt.


Nachdem Sie die Richtliniendefinition erstellt oder aktualisiert haben, können Sie sie einem Benutzer zuweisen, indem Sie auf der Richtlinienseite **Benutzer verwalten** auswählen, nach dem gewünschten Benutzer suchen und dann die Richtlinie anwenden.

![Bereich „Benutzer verwalten“ auf der rechten Seite, oben auf der Seite mit den Nachrichtenrichtlinien.](media/edu-manage-users-pane.png)

Sie können einem Benutzer auch eine Richtlinie zuweisen, indem Sie zu **Benutzer** navigieren, den Benutzer, für den Sie Richtlinien aktualisieren möchten, **Richtlinien** und dann **Bearbeiten** auswählen. Dort können Sie die Richtliniendefinition auswählen, die Sie dem Benutzer für jeden Fähigkeitenbereich zuweisen möchten.

![Bereich „Benutzerrichtlinien bearbeiten“ rechts auf der Seite „zugewiesene Richtlinien“.](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a>Richtlinienpakete in Microsoft Teams
> [!NOTE]
> Weitere Informationen finden Sie unter [Richtlinienpakete in Microsoft Teams verwalten](manage-policy-packages.md), wo Sie auch eine Schritt-für-Schritt-Anleitung zum Zuweisen eines Pakets an einzelne Benutzer, zum Zuweisen von Paketen in großen Mengen an bis zu 5.000 Benutzer sowie zum Verwalten und Aktualisieren der Richtlinien finden, die mit jedem Paket verknüpft sind.

Ein Richtlinienpaket in Teams kombiniert vordefinierte Richtlinien und Richtlinieneinstellungen, die Sie über die oben beschriebenen Vorgehensweisen kennengelernt haben, und weist sie Benutzern mit ähnlichen Rollen in Ihrer Einrichtung zu. Richtlinienpakete vereinfachen und rationalisieren Richtlinien und lassen Sie diese konsistent verwalten. Üblicherweise weisen Sie jedem Ihrer Benutzer ein Richtlinienpaket zu und definieren die Richtlinien in jedem Paket entsprechend der Anforderungen dieser Benutzergruppe neu. Wenn Sie die Einstellungen in einem Paket aktualisieren, werden diese Einstellungen für alle Benutzer, denen dieses Paket zugeordnet ist, geändert.

Bildungseinrichtungen im Allgemeinen haben viele Benutzer mit individuellen Bedürfnissen, je nach Alter und Reife der Schüler. So möchten Sie beispielsweise Lehrkräften und Mitarbeitern Vollzugriff auf Microsoft Teams gewähren, die Funktionen von Microsoft Teams aber einschränken, um eine sichere und fokussierte Lernumgebung für Schüler zu fördern. Sie können Richtlinienpakete verwenden, um die Einstellungen entsprechend der Anforderungen unterschiedlicher Kohorten in Ihrer Bildungseinrichtung anzupassen.

> [!IMPORTANT] 
> Unsere Hauptempfehlung ist, dass Sie statt eines Richtlinienpakets die globale (organisationsweiter Standard) Richtliniendefinition für Lernende verwenden. Dadurch wird sichergestellt, dass neue Benutzer in Ihrer Organisation immer über den strengsten Richtliniensatz für Lernende verfügen. Wenn diese Empfehlung nicht den Anforderungen Ihrer Institution entspricht, kann eines der unten aufgeführten Lernenden-Richtlinienpakete eine gute Alternative sein. 

Ähnlich wie die Richtlinienliste weiter oben in diesem Artikel definieren Richtlinienpakete Richtlinien für:

- Besprechungen
- Liveereignisse
- Anrufe
- Messaging
- App-Berechtigungen

Microsoft Teams umfasst derzeit die folgenden Richtlinienpakete:

|Paketname im Microsoft Teams Admin Center |Am besten geeignet für  |Beschreibung |
|:--- |:--- |:--- |
|**Education_Teacher**| Lehrkräfte und Mitarbeiter| Verwenden Sie diese Richtlinien und Richtlinieneinstellungen, um Lehrern und Mitarbeitern in Ihrer Organisation Vollzugriff auf Chats, Anrufe und Besprechungen über Microsoft Teams zu gewähren. |
|**Education_PrimaryStudent**| Schüler im Grundschulalter  | Jüngere Schüler im Grundschulalter innerhalb Ihrer Institution benötigen möglicherweise mehr Beschränkungen innerhalb von Microsoft Teams. Verwenden Sie diesen Richtliniensatz und diese Richtlinieneinstellungen, um Funktionen wie die Erstellung und Verwaltung von Besprechungen, die Chatverwaltung und private Anrufe einzuschränken. |
|**Education_SecondaryStudent**| Schüler in der Altersgruppe weiterführender Schulen | Schüler in der Altersgruppe weiterführender Schulen innerhalb Ihrer Institution benötigen möglicherweise mehr Beschränkungen innerhalb von Microsoft Teams. Verwenden Sie diesen Richtliniensatz und diese Richtlinieneinstellungen, um Funktionen wie die Erstellung und Verwaltung von Besprechungen, die Chatverwaltung und private Anrufe einzuschränken. |
|**Education_HigherEducationStudent**| Hochschul-Studenten | Hochschul-Studenten innerhalb Ihrer Intuition benötigen möglicherweise weniger Einschränkungen als jüngere Schüler, aber einige Begrenzungen könnten dennoch angeraten sein. Sie können diesen Richtliniensatz und diese Richtlinieneinstellungen verwenden, um den Zugriff auf Chats, Anrufe und Besprechungen innerhalb Ihrer Organisation zu gewähren, aber einschränken, wie Ihre Schüler Microsoft Teams mit externen Teilnehmern verwenden. |
|**Education_PrimaryTeacher_RemoteLearning**| Lehrkräfte und Mitarbeiter | Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Lehrkräfte beim Lernen per Fernzugriff zu maximieren. |
|**Education_PrimaryStudent_RemoteLearning**| Schüler im Grundschulalter| Erstellt eine Reihe von Richtlinien, um die Sicherheit und Zusammenarbeit der Schüler beim Lernen per Fernzugriff zu maximieren.
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="Seite „Richtlinienpakete“ mit einer Liste von Richtlinienpaketen zur Auswahl.":::

Jeder einzelnen Richtlinie wird mit dem Namen des Richtlinienpakets versehen, damit Sie mit einem Richtlinienpaket verknüpfte Richtlinien leicht erkennen können. Wenn Sie das Richtlinienpaket „Education_Teacher“ beispielsweise Lehrkräften in Ihrer Bildungseinrichtung zuweisen, wird für jede Richtlinie im Paket eine Richtlinie namens „Education_Teacher“ erstellt.

![Screenshot des Education_Teacher-Richtlinienpakets](media/policy-packages-education_teacher.png)

> [!NOTE]
> Wenn Sie beschließen, dass Lehrkräfte und administrative Mitarbeiter unterschiedliche Richtlinien benötigen, können Sie ein vorhandenes Paket neu verwenden: ermitteln Sie ein Paket, das Sie derzeit nicht verwenden, und ändern Sie die Einstellungen so, dass sie für diese Gruppe geeignet sind. Möglicherweise müssen Sie eine Notiz für sich selbst erstellen, welcher Gruppe welches Paket zugeordnet ist, doch das ist der einzige „Nachteil“ der Neunutzung eines Pakets.

## <a name="manage-policy-packages"></a>Verwalten von Richtlinienpaketen

### <a name="view"></a>Anzeigen

Sehen Sie sich die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers **Richtlinienpakete** aus, dann den gewünschten Paketnamen und schließlich den Namen der Richtlinie.

Überprüfen Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind, oder ob Sie sie mehr oder weniger restriktiv einstellen müssen, damit sie den Anforderungen Ihrer Organisation entsprechen.

### <a name="customize"></a>Anpassung

Passen Sie die Einstellungen von Richtlinien im Richtlinienpaket ggf. an die Anforderungen Ihrer Organisation an. Alle Änderungen, die Sie an den Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen wird. Wenn Sie die Einstellungen einer Richtlinie in einem Richtlinienpaket bearbeiten möchten, wählen Sie im Microsoft Teams Admin Center das entsprechende Richtlinienpaket und dann den Namen der Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie anschließend **Bearbeiten** aus.

Sie können die Einstellungen für Richtlinien in einem Paket auch ändern, nachdem Sie das Richtlinienpaket zugewiesen haben. Weitere Informationen hierzu finden Sie unter [Anpassen von Richtlinien in einem Richtlinienpaket](manage-policy-packages.md#customize-policies-in-a-policy-package). 

### <a name="assign"></a>Zuweisen

Weisen Sie das Richtlinienpaket Benutzern zu. Wenn einem Benutzer eine Richtlinie zugewiesen wurde und Sie ihm dann später eine andere Richtlinie zuweisen, hat die neuere Vorrang.

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>Ein Richtlinienpaket einem oder mehreren Benutzern zuweisen

Um einem oder mehreren Benutzern ein Richtlinienpaket zuzuweisen, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zu **Richtlinienpakete** , und wählen Sie dann **Benutzer verwalten** aus.  

![Screenshot zur Vorgehensweise zum Zuweisen eines Richtlinienpakets im Admin Center](media/policy-packages-healthcare-assign.png)

Weitere Informationen hierzu finden Sie unter [Zuweisen eines Richtlinienpakets](manage-policy-packages.md#assign-a-policy-package).

Wenn einem Benutzer eine Richtlinie zugewiesen wurde und Sie ihm dann später eine andere Richtlinie zuweisen, hat die neuere Vorrang.

#### <a name="assign-a-policy-package-to-a-group"></a>Ein Richtlinienpaket einer Gruppe zuweisen

**Dieses Feature ist derzeit lediglich als private Vorschau verfügbar**

Die Gruppenzuweisung von Richtlinienpaketen ermöglicht es Ihnen, mehrere Richtlinien einer Gruppe von Benutzern wie z. B. einer Sicherheitsgruppe oder einer Verteilerliste zuzuweisen. Die Richtlinienzuweisung wird anhand von Prioritätsregeln an die Mitglieder der Gruppe weitergegeben. Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert. Diese Methode wird für Gruppen mit bis zu 50.000 Benutzern empfohlen, sie eignet sich aber auch für größere Gruppen.

Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einer Gruppe zuweisen](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Ein Richtlinienpaket einer großen Anzahl von Benutzern (Batch) zuweisen

Wenn Sie ein Richtlinienpaket einer großen Anzahl von Benutzern gleichzeitig zuweisen möchten, verwenden Sie hierfür die Richtlinienpaket-Batch-Zuweisung. Verwenden Sie das Cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation), um einen Benutzer-Batch und das Richtlinienpaket zu senden, das Sie zuweisen möchten. Die Zuweisungen werden als Hintergrundvorgänge verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.

Ein Batch kann bis zu 5.000 Benutzer umfassen. Sie können Benutzer durch Angabe ihrer Objekt-ID, des UPN, der SIP-Adresse oder der E-Mail-Adresse hinzufügen. Weitere Informationen hierzu finden Sie unter [Ein Richtlinienpaket einem Batch von Benutzern zuweisen](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="policies-that-should-be-assigned-for-student-safety"></a>Richtlinien, die zum Schutz von Schülern und Studenten zugewiesen werden sollten

Weitere Informationen zu den Schritten, die Sie zum Schutz der Lernenden in Ihrer Umgebung ergreifen müssen, finden Sie unter [Die Sicherheit der Lernenden beim Einsatz von Teams für den Fernunterricht gewährleisten](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8).
