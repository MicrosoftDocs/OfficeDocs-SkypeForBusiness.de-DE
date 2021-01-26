---
title: Verwalten der App "Aufgaben" für Ihre Organisation in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
audience: admin
description: Erfahren Sie, wie Sie die App "Aufgaben" für Benutzer in Ihrer Organisation verwalten.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cc477b9589aeebb8dcd486e7f85ca04daf6ff4d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909399"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Verwalten der App "Aufgaben" für Ihre Organisation in Microsoft Teams

## <a name="overview-of-tasks"></a>Übersicht über Aufgaben

Die App "Aufgaben" bietet Microsoft Teams eine 1:1-Erfahrung beim Aufgabenmanagement, indem einzelne Aufgaben, die von [Microsoft To Do](https://todo.microsoft.com/tasks/) unterstützt werden, und Teamaufgaben, die von Planner unterstützt werden, an einer Stelle integriert werden. Benutzer können auf Aufgaben als App auf der linken Seite von Teams und als Registerkarte in einem Kanal innerhalb einzelner Teams zugreifen. **Mit "Meine Aufgaben"** **und "Freigegebene** Pläne" in "Aufgaben" können Benutzer alle ihre Einzel- und Teamaufgaben anzeigen und verwalten sowie ihre Arbeit priorisieren. Aufgaben stehen in Desktop-, Web- und mobilen Clients von Teams zur Verfügung. 

> [!NOTE]
> Beim Rollout der Aufgabenerfahrung auf Teams-Desktopclients wird der Name der App den Benutzern zunächst **als Planner** angezeigt. Der Name wird dann von Planner und **To Do** vorübergehend in "Aufgaben" geändert und später in "Aufgaben" **umbenannt.** Auf mobilen Teams-Clients wird den Benutzern der Name der App immer als **"Aufgaben" angezeigt.** Es kann eine kurze Verzögerung bei der Verfügbarkeit der mobilen Benutzererfahrung kommen, nachdem die Desktoperfahrung verfügbar ist.

   ![Screenshot der Listenansicht von Aufgaben in der Liste "Teams"](media/manage-tasks-app-tasks.png)

Organisationen, die die Aufgabenverwaltung für Frontlinemitarbeiter optimieren möchten, umfasst Aufgaben auch Funktionen, die es Ihnen ermöglichen, Aufgaben in der gesamten Belegschaft an vorder frontline zu übernehmen, zu veröffentlichen und nachverfolgt zu können. So können Führungskräfte aus Unternehmen und Regionen beispielsweise Aufgabenlisten erstellen und veröffentlichen, die an relevante Orte ausgerichtet sind, z. B. bestimmte Einzelhandelsgeschäfte, und den Fortschritt mithilfe von Echtzeitberichten nachverfolgen. Vorgesetzte können ihren Mitarbeitern Aufgaben zuweisen und direkt Aktivitäten an ihren Standorten ausführen, und Frontlinemitarbeiter verfügen über eine priorisierte Liste der ihnen zugewiesenen Aufgaben auf mobilen Geräten oder auf dem Desktop. Um die [Veröffentlichung von](#task-publishing)Aufgaben zu aktivieren, müssen Sie zuerst eine Teamzielhierarchie für Ihre Organisation einrichten, die definiert, wie alle Teams in der Hierarchie miteinander verknüpft sind.

## <a name="what-you-need-to-know-about-tasks"></a>Was Sie über Aufgaben wissen müssen

Aufgaben stehen als App und als Registerkarte in einem Kanal zur Verfügung. Denken Sie daran, dass die App sowohl einzelne Aufgaben aus "Aufgaben" als auch Teamaufgaben aus Planner umfasst, während auf der Registerkarte nur Teamaufgaben angezeigt werden.

Mit "Aufgaben" erhalten Benutzer eine Desktop-, Web- und mobile Erfahrung. Wenn "Aufgaben" auf dem Desktopclient von Teams installiert ist, wird sie den Benutzern auch auf ihren Web- und mobilen Teams-Clients angezeigt. Die Ausnahme bilden Gastbenutzer. Es ist wichtig zu wissen, dass Gäste über den mobilen Client von Teams nur als App auf Aufgaben zugreifen können. Gästen werden die Registerkarten "Aufgaben" sowohl auf der Desktop- als auch der Webclients von Teams angezeigt.

**Meine Aufgaben** zeigen die einzelnen Aufgaben eines Benutzers an. **Freigegebene** Pläne zeigen Aufgaben an, an der das gesamte Team arbeitet, und enthalten alle Aufgabenlisten, die einem Kanal als Registerkarte "Aufgaben" hinzugefügt wurden. Beachten Sie Folgendes:

- Aufgabenlisten, die ein Benutzer in der App "Aufgaben" erstellt, werden auch in den Aufgabenclients für den Benutzer angezeigt. Ebenso werden Aufgabenlisten, die ein Benutzer in "Aufgaben" erstellt, unter "Meine **Aufgaben"** in "Aufgaben" für den Benutzer angezeigt. Dasselbe gilt für einzelne Vorgänge.

- Alle Registerkarten "Aufgaben", die einem Kanal hinzugefügt wurden, werden auch in den Planner-Clients angezeigt. Wenn ein Benutzer in Planner einen Plan erstellt, wird er nicht in der Aufgaben- oder der Planner-App angezeigt, es sei denn, er wurde als Registerkarte zu einem Kanal hinzugefügt. Wenn ein Benutzer eine neue Registerkarte "Aufgaben" hinzufügt, kann er eine neue Liste oder einen neuen Plan erstellen oder eine vorhandene auswählen.

## <a name="set-up-tasks"></a>Einrichten von Aufgaben

> [!IMPORTANT]
> Einstellungen und Richtlinien, die Sie für Planner konfiguriert haben, gelten auch für Aufgaben.

### <a name="enable-or-disable-tasks-in-your-organization"></a>Aktivieren oder Deaktivieren von "Aufgaben" in Ihrer Organisation

Aufgaben sind standardmäßig für alle Benutzer von Teams in Ihrer Organisation aktiviert. Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](manage-apps.md) deaktivieren oder aktivieren.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Führen Sie in der Liste der Apps einen der folgenden Schritte aus:

    - Um "Aufgaben" für Ihre Organisation zu deaktivieren, suchen Sie nach der Aufgaben-App, wählen Sie sie aus, und klicken Sie dann auf **"Blockieren".**
    - Um "Aufgaben" für Ihre Organisation zu aktivieren, suchen Sie nach der Aufgaben-App, wählen Sie sie aus, und klicken Sie dann auf **"Zulassen".**

> [!NOTE]
> Wenn Sie die App "Aufgaben" nicht finden können, suchen Sie nach den Namen in der ersten Notiz dieses Artikels. Die App kann gerade umbenannt werden.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>Aktivieren oder Deaktivieren von "Aufgaben" für bestimmte Benutzer in Ihrer Organisation

Um bestimmten Benutzern in Ihrer Organisation die Verwendung von "Aufgaben" zu [](manage-apps.md) gestatten oder zu blockieren, stellen Sie sicher, dass "Aufgaben" für Ihre Organisation auf der Seite "Apps verwalten" aktiviert ist. Erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie sie diesen Benutzern zu. Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>Verwenden einer App-Setup-Richtlinie zum Anheften von Aufgaben an Teams

Mithilfe von App-Setup Richtlinien können Sie Microsoft Teams so anpassen, dass die Apps, die für die Benutzer in Ihrer Organisation am wichtigsten sind, hervorgehoben werden. Die Apps, die Sie in einer Richtlinie festlegen, sind an der Leiste der App an der Seite des Teams-Desktopclients und am unteren Rand der mobilen Teams-Clients angeheftet, wo Benutzer schnell und einfach darauf zugreifen &mdash; &mdash; können.

Zum Anheften der Aufgaben-App für Ihre Benutzer können Sie die globale Richtlinie (organisationsweite Standardrichtlinie) bearbeiten oder eine benutzerdefinierte App-Setuprichtlinie erstellen und zuweisen. Weitere Informationen finden Sie unter "Verwalten von [Richtlinien für das Einrichten von Apps in Teams".](teams-app-setup-policies.md)

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>"Meine Aufgaben" eines Benutzers wird angezeigt, wenn der Benutzer für Exchange Online lizenziert ist.

Wenn einem Benutzer "Meine Aufgaben" nicht angezeigt werden **soll,** können Sie ihn ausblenden. Entfernen Sie dazu [die Exchange Online-Lizenz des Benutzers.](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) Es ist wichtig zu wissen, dass der Benutzer nach dem Entfernen einer Exchange Online-Lizenz keinen Zugriff mehr auf sein Postfach hat.  Postfachdaten werden 30 Tage lang gespeichert, danach werden die Daten entfernt und können nicht wiederhergestellt werden, es sei denn, das Postfach wird in einem In-Place-Hold- oder Litigation Hold [platziert.](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

Wir empfehlen dies nicht für Information Workers, aber es gibt möglicherweise einige Szenarien, in denen dies gelten könnte, z. B. für Frontline-Mitarbeiter, die nicht auf E-Mails angewiesen sind.

## <a name="task-publishing"></a>Veröffentlichung von Aufgaben

Mit der Veröffentlichung von Aufgaben kann Ihre Organisation Aufgabenlisten veröffentlichen, die an bestimmte Orte (Teams) in der gesamten Organisation ausgerichtet sind, um einen an diesen Orten auszuführende Arbeitsplan zu definieren und gemeinsam zu verwenden.

- Personen im Veröffentlichungsteam, z. B. Unternehmens- oder Regionalführungsteams, können Aufgabenlisten erstellen und in bestimmten Teams veröffentlichen.<br>
    ![Screenshot der Vorgangsveröffentlichung](media/manage-tasks-app-publish.png)
- Die Manager der Empfängerteams können die veröffentlichten Aufgabenlisten überprüfen und einzelnen Teammitgliedern Aufgaben zuweisen.<br>
    ![Screenshot zum Zuweisen einer Aufgabe](media/manage-tasks-app-assign.png)
- Mitarbeiter an vorderen Fronten verfügen über eine einfache mobile Erfahrung, um ihnen zugewiesene Aufgaben zu sehen. Sie können Fotos anfügen, um ihre Arbeit gegebenenfalls zu zeigen und ihre Aufgaben als erledigt zu kennzeichnen.
- Herausgeber und Manager können Berichte anzeigen, um den Zuordnungs- und Abschlussstatus von Aufgaben auf jeder Ebene, einschließlich nach Ort (Team), Aufgabenliste und einzelner Aufgabe, zu sehen.<br>
    ![Screenshot der zugewiesenen Aufgaben auf einem mobilen Gerät](media/manage-tasks-app-reporting.png)

Benutzer erstellen, verwalten und veröffentlichen Aufgabenlisten auf der Registerkarte "Veröffentlichte **Listen"** in der Aufgaben-App. Diese Registerkarte wird nur für [](#set-up-your-team-targeting-hierarchy) einen Benutzer angezeigt, wenn Ihre Organisation eine Teamzielhierarchie eingerichtet hat und der Benutzer zu einem Team gehört, das in der Hierarchie enthalten ist. Die Hierarchie bestimmt, ob der Benutzer Aufgabenlisten veröffentlichen oder empfangen und Berichte für empfangene Listen anzeigen kann.

### <a name="example-scenario"></a>Beispielszenario

Hier ist ein Beispiel für die Funktionsweise der Aufgabenveröffentlichung.

Contoso bietet eine neue Werbeaktion für Lebensmittelzustellung und Lieferung an. Um eine konsistente Markenerfahrung zu erhalten, müssen sie die konsistente Durchführung des Rollouts für mehr als 300 Store-Standorte koordinieren.

Das Marketingteam teilt die Promotiondetails und die entsprechende Aufgabenliste mit dem Retail Communications Manager. Der Retail Communications Manager, der als Gatekeeper für Filialen dient, überprüft die Informationen, erstellt eine Aufgabenliste für die Werbeaktion und erstellt dann eine Aufgabe für jede Arbeitseinheit, die von jedem der betroffenen Stores ausgeführt werden muss. Nach Abschluss der Aufgabenliste muss sie die Filialen auswählen, die die Arbeit abschließen müssen. In diesem Fall gilt die Werbeaktion nur für Filialen in den USA, die über ein In-Store-Restaurant verfügen. In "Aufgaben" filtert sie die Liste der Filialen basierend auf dem Attribut "Restaurant im Laden", wählt die übereinstimmenden Standorte in der Hierarchie aus und veröffentlicht die Aufgabenliste dann in diesen Stores.

Die Manager von Filialen erhalten an jedem Standort eine Kopie der veröffentlichten Aufgaben und weisen diese Aufgaben ihren Teammitgliedern zu. Vorgesetzte können die Aufgabenerfahrung nutzen, um die gesamte in ihrem Geschäft erforderliche Arbeit zu verstehen. Sie können auch die verfügbaren Filter verwenden, um sich auf eine bestimmte Gruppe von Arbeiten zu konzentrieren, z. B. auf heute fällige Arbeit oder Arbeit in einem bestimmten Bereich.

Mitarbeiter an vorderen Frontlinien an jedem Standort eines Ladengeschäfts verfügen jetzt über eine priorisierte Liste ihrer Arbeit unter "Aufgaben" auf ihrem mobilen Gerät. Wenn sie eine Aufgabe abgeschlossen haben, markieren sie sie als "Abgeschlossen". Einige entscheiden sich möglicherweise sogar dafür, ein Foto hochzuladen und an die Aufgabe anfügen, um ihre Arbeit zu zeigen.

Die Zentrale von Contoso und Vorgesetzte für Fortgeschrittene können Berichte anzeigen, um den Zuordnungs- und Abschlussstatus von Vorgängen in jedem Ladengeschäft und in allen Filialen zu sehen. Sie können auch einen Drilldown zu einer bestimmten Aufgabe erstellen, um den Status in verschiedenen Stores zu sehen. Wenn das Startdatum näher rückt, können sie ungewöhnliche Veröffentlichungen erkennen und sich bei Bedarf bei ihren Teams einchecken. Diese Sichtbarkeit ermöglicht Es Contoso, die Effizienz des Rollouts zu verbessern und eine einheitlichere Benutzererfahrung für alle Stores zu bieten.

### <a name="set-up-your-team-targeting-hierarchy"></a>Einrichten der Teamzielhierarchie

Um die Veröffentlichung von Aufgaben in Ihrer Organisation zu aktivieren, müssen Sie zuerst Ihr Teamzielschema in einem einrichten. "CSV-Datei" aus. Das Schema definiert, wie alle Teams in Ihrer Hierarchie miteinander in Beziehung stehen und welche Attribute zum Filtern und Auswählen von Teams verwendet werden. Nachdem Sie das Schema erstellt haben, laden Sie es in Teams hoch, um es auf Ihre Organisation anzuwenden. Mitglieder des Veröffentlichungsteams, z. B. Retail Communications Manager im Beispielszenario, können teams dann nach Hierarchie, Attributen oder einer Kombination aus beiden filtern, um die relevanten Teams auszuwählen, die die Aufgabenlisten erhalten sollen, und die Aufgabenlisten dann für diese Teams zu veröffentlichen.

Schritte zum Einrichten der Hierarchie für Teamzielierung finden Sie unter ["Einrichten der Teamzielhierarchie".](set-up-your-team-hierarchy.md)

## <a name="power-automate-and-graph-api"></a>Power Automate- und Graph-API

Aufgaben unterstützen Power Automate for To Do- und Graph-APIs für Planner. Weitere Informationen finden Sie unter:

- [Übersicht über die API für Aufgaben und Pläne von Planner](https://docs.microsoft.com/graph/planner-concept-overview)
- [Verwenden von Microsoft To Do mit Power Automate](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
