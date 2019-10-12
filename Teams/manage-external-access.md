---
title: Verwaltung des externen Zugriffs (Verbund) in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/12/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.externalaccess.overview
description: Ihr IT-Administrator kann den externen Zugriff für andere Domänen (Verbund) so konfigurieren, dass Benutzer aus diesen Domänen in Teams teilnehmen können.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: f2252b14343aa68e4a1dd97bc918b5c9cc30d727
ms.sourcegitcommit: e84becc101232b8017aab519378480c5dbebbb48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2019
ms.locfileid: "37468498"
---
<a name="manage-external-access-in-microsoft-teams"></a>Verwaltung des externen Zugriffs in Microsoft Teams
======================================================

Mit dem externen Zugriff auf Microsoft Teams können Teams-Benutzer aus anderen Domänen an ihren Chats und Anrufen teilnehmen. Sie können auch anderen externen Benutzern, die noch Skype for Business Online, Skype for Business (lokal) oder sogar Skype verwenden, die Teilnahme gestatten.

Verwenden Sie den externen Zugriff in folgenden Fällen:
  
- In Ihrem Unternehmen befinden sich Benutzer in verschiedenen Domänen. Beispiel: Rob@contoso.com und Ann@northwindtraders.com.

- Sie möchten den Personen in Ihrer Organisation die Möglichkeit geben, Microsoft Teams zu verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.

- Sie möchten, dass alle anderen Microsoft Teams-Benutzer aus aller Welt Sie anhand Ihrer E-Mail-Adresse finden und Kontakt zu Ihnen aufnehmen können. Wenn Sie und ein anderer Benutzer sowohl den externen Zugriff aktivieren als auch die Domänen des anderen zulassen, funktioniert das. Wenn es nicht funktioniert, sollte der andere Benutzer sich vergewissern, dass seine Konfiguration Ihre Domäne nicht blockiert.

Externer Zugriff ermöglicht externen Benutzern das Auffinden, Anrufen und Senden von Chatnachrichten sowie das Einrichten von Besprechungen mit Ihnen. Wenn Sie externen Benutzern hingegen den Zugriff auf Teams und Kanäle gewähren möchten, ist der Gastzugriff möglicherweise besser geeignet. Weitere Informationen zu den Unterschieden zwischen externem Zugriff und Gastzugriff finden Sie unter [Externer Zugriff und Gastzugriff im Vergleich](#external-access-vs-guest-access) weiter unten. Informationen zum Aktivieren des Gastzugriffs, um Benutzern zu ermöglichen, miteinander zu kommunizieren, finden Sie unter [Aktivieren des Gastzugriffs](set-up-guests.md).

> [!IMPORTANT]
> Um innerhalb der Microsoft Teams-App einen Verbund mit einem externen Benutzer außerhalb Ihrer Organisation zu erstellen, der derzeit kein Gastbenutzer in Azure Active Directory (Azure AD) oder Mandant ist, müssen Sie ordnungsgemäß für Hybridumgebungen konfiguriert und bereits auf Skype for Business Online umgestiegen sein. Seit dem 25.2.2019 unterstützt Microsoft Teams keinen nativen Verbund, ohne dass der Benutzer des SIP-Profils in Skype for Business Online verwaltet wird. Weitere Informationen dazu, wie Sie Ihr Konto für die Hybridumgebung einrichten und dann zu Teams wechseln, finden Sie unter [Upgrade von einer Skype for Business-Hybridbereitstellung zu Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

> [!IMPORTANT]
> Gastbenutzer folgen den organisationsweiten Einstellungen für den Koexistenzmodus. Dies kann nicht geändert werden.

## <a name="external-access-vs-guest-access"></a>Externer Zugriff und Gastzugriff im Vergleich

Externer Zugriff (Verbund) und Gastzugriff unterscheiden sich:

- Gastzugriff gewährt einer Person Zugriffsberechtigungen. Externer Zugriff gewährt einer kompletten Domäne Zugriffsberechtigungen.

- Sobald der Gastzugriff von einem Teambesitzer gewährt wurde, bietet er einem Gastbenutzer die Möglichkeit, [auf Ressourcen eines bestimmten Teams zuzugreifen](guest-experience.md), z. B. Diskussionen und Dateien in einem Kanal, und mit anderen Benutzern in dem Team zu chatten, zu dem er eingeladen wurde. Beim externen Zugriff (Verbundchat) haben die Teilnehmer des externen Chats keinen Zugriff auf die Teams oder Teamressourcen der einladenden Organisation. Sie können nur an einem einzelnen 1:1-Verbundchat teilnehmen. Mandantenadministratoren können zwischen den beiden Kommunikationsoptionen auswählen, je nachdem, welche Ebene der Zusammenarbeit für den externen Partner gewünscht wird. Administratoren können, je nach den Anforderungen Ihrer Organisation, einen oder beide Ansätze wählen, aber es empfiehlt sich, für eine umfassendere und kooperativere Microsoft Teams-Erfahrung den Gastzugriff zu aktivieren. 

In der folgenden Tabelle finden Sie einen Vergleich der Features des externen Zugriffs und des Gastzugriffs.

| Feature | Benutzer mit externem Zugriff | Benutzer mit Gastzugriff |
|---------|-----------------------|--------------------|
| Der Benutzer kann mit jemandem in einem anderen Unternehmen chatten. | Ja |Ja |
| Der Benutzer kann jemanden in einem anderen Unternehmen anrufen | Ja | Ja |
| Der Benutzer kann sehen, ob jemand aus einem anderen Unternehmen für Anrufe oder Chats verfügbar ist | Ja | Ja<sup>1</sup> |
| Der Benutzer kann auf externen Mandanten nach Benutzern suchen | Ja<sup>2</sup> | Nein |
| Der Benutzer kann Dateien freigeben | Nein | Ja |
| Der Benutzer kann auf Microsoft Teams-Ressourcen zugreifen | Nein | Ja |
| Der Benutzer kann zu einem Gruppenchat hinzugefügt werden | Nein | Ja |
| Der Benutzer kann zu einer Besprechung hinzugefügt werden | Ja | Ja |
| Weitere Benutzer können zu einem Chat mit einem externen Benutzer hinzugefügt werden | No<sup>3</sup> | Nicht zutreffend |
| Der Benutzer wird als externer Partner gekennzeichnet | Ja | Ja |
| Anwesenheit wird angezeigt | Ja | Ja |
| Abwesenheitsnachricht wird angezeigt | Nein | Ja |
| Ein einzelner Benutzer kann blockiert werden | Nein | Nein |
| @Mentions werden unterstützt | Nein | Ja |
| Private Anrufe führen | Ja | Ja |
| IP-Video zulassen | Ja | Ja |
| Bildschirmfreigabemodus | Nein | Ja |
| Sofortbesprechungen zulassen | Nein | Ja |
| Gesendete Nachrichten bearbeiten | Nein | Ja |
| Löschen gesendeter Nachrichten möglich | Nein | Ja |
| Giphy in Unterhaltung verwenden | Nein | Ja |
| Memes in Unterhaltung verwenden | Nein | Ja |
| Sticker in Unterhaltung verwenden | Nein | Ja |
||||

<sup>1</sup> Vorausgesetzt, der Benutzer wurde als Gast hinzugefügt und hat sich als Gast beim Gastmandanten angemeldet.<br>
<sup>2</sup> Nur per E-Mail- oder SIP-Adresse (Session Initiation Protocol).<br>
<sup>3</sup> Externer Chat (Verbundchat) nur 1:1.

Weitere Informationen zu Gastfeatures und der Gastumgebung finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) und [Ablauf für den Gast](https://docs.microsoft.com/microsoftteams/guest-experience).

Weitere Informationen zur kostenlosen Version von Microsoft Teams und deren Funktionsweise mit Features von "Externer Zugriff" finden Sie unter [Unterschiede zwischen Microsoft Teams und der kostenlosen Version von Microsoft Teams](https://support.office.com/article/differences-between-microsoft-teams-and-microsoft-teams-free-0b69cf39-eb52-49af-b255-60d46fdf8a9c?ui=en-US&rs=en-US&ad=US).

## <a name="quick-steps-for-scenarios"></a>Schnelle Schritte für Szenarien

|**Ziel**  |**Kurzanleitung**  |
|---------|-----------------------|
|Sie möchten **Microsoft Teams-Benutzern** in Ihrer Organisation die Kommunikation mit **Microsoft Teams-Benutzern** in einer anderen (externen) Organisation ermöglichen.|Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund". <p>Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen.      |
|Sie möchten **Microsoft Teams-Benutzern** in Ihrer Organisation die Kommunikation mit **Skype for Business Online-Benutzern** in derselben Organisation ermöglichen.  |Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Upgrademodus "Inseln" aus, um die Skype for Business-Benutzer in Ihrer Organisation zu unterstützen.   |
|Sie möchten **Microsoft Teams-Benutzern** in Ihrer Organisation die Kommunikation mit **Skype for Business Online-Benutzern** in einer anderen (externen) Organisation ermöglichen.      |Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund".  <p>Aktivieren Sie die Einstellung **Benutzer können mit Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff". <p>Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen. <p>**HINWEIS**: In der externen Domäne mit Skype for Business-Benutzern muss der Koexistenzmodus aktiviert oder der Upgrademodus "Inseln" ausgewählt werden, um die Skype for Business-Benutzer in dieser Organisation zu unterstützen.|
|Sie möchten **Microsoft Teams-Benutzern** in Ihrer Organisation die Kommunikation mit **Skype**-Benutzern innerhalb oder außerhalb Ihrer Organisation ermöglichen.   | Derzeit kein unterstütztes Szenario. <p>**WICHTIG**: Ihre Microsoft Teams-Benutzer sind nicht in der Lage, mit Skype-Benutzern zu kommunizieren, aber die Skype for Business-Benutzer in Ihrer Organisation können mit Skype-Benutzern innerhalb oder außerhalb Ihrer Organisation kommunizieren, wenn diese beiden Voraussetzungen erfüllt sind: <p>1) Aktivieren Sie die Einstellungen **Benutzer können mit Skype for Business- und Teams-Benutzern kommunizieren** und **Skype for Business-Benutzer können mit Skype-Benutzern kommunizieren** unter "Externer Zugriff". <p> 2) Ihre Organisation wird im Koexistenzmodus ausgeführt. |
|Sie möchten Ihren **Microsoft Teams-Benutzern** die Kommunikation mit **Skype for Business Online-Benutzern** aus einer lokalen Organisation sowie mit **Skype-Benutzern** ermöglichen.   |Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund". . <p>Aktivieren Sie die Einstellung **Benutzer können mit Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff". <p>Aktivieren Sie die Einstellung **Skype for Business-Benutzer können mit Skype-Benutzern kommunizieren** unter "Externer Zugriff". <p> Lassen Sie dann den Administrator in der lokalen Organisation dieselben Schritte ausführen.<p>**WICHTIG**: In diesem Szenario können Ihre Microsoft Teams-Benutzer nicht mit Skype-Benutzern kommunizieren, aber Skype for Business-Benutzer in Ihrer Organisation können mit Skype-Benutzern innerhalb oder außerhalb Ihrer Organisation kommunizieren, wenn Sie die Einstellungen **Benutzer können mit Skype for Business- und Teams-Benutzern kommunizieren** und **Skype for Business-Benutzer können mit Skype-Benutzern kommunizieren** unter "Externer Zugriff" aktivieren.|
|Sie möchten Ihren **Skype for Business Online-Benutzern** die Kommunikation mit **Microsoft Teams-Benutzern** in einer anderen Office 365-Organisation ermöglichen.|Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Upgrademodus "Inseln" aus, um die Skype for Business-Benutzer in Ihrer Organisation zu unterstützen. <p>Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund".  <p> Aktivieren Sie die Einstellung **Benutzer können mit Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff". <p>Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen. |
|Sie möchten Ihren **Skype for Business Online-Benutzern** die Kommunikation mit den **Skype for Business Online-Benutzern** aus einer anderen Office 365-Organisation ermöglichen.    | Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Upgrademodus "Inseln" aus, um die Skype for Business-Benutzer in Ihrer Organisation zu unterstützen. <p>Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund". <p> Aktivieren Sie die Einstellung **Benutzer können mit Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff".<p>Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen. |
|Sie möchten Ihren **Skype for Business Online-Benutzern** die Kommunikation mit den **Skype for Business Online-Benutzern** aus einer lokalen Organisation ermöglichen.     |Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Upgrademodus "Inseln" aus, um die Skype for Business-Benutzer in Ihrer Organisation zu unterstützen. <p>Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund".  <p>Aktivieren Sie die Einstellung **Benutzer können mit Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff".  <p> Lassen Sie dann den Administrator in der lokalen Organisation dieselben Schritte ausführen. |
|Sie möchten Ihren **Skype for Business Online-Benutzern** die Kommunikation mit **Skype-Benutzern** (innerhalb oder außerhalb Ihrer Organisation) ermöglichen.   |Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Upgrademodus "Inseln" aus, um die Skype for Business-Benutzer in Ihrer Organisation zu unterstützen. <p>Aktivieren Sie die Einstellung **Skype for Business-Benutzer können mit Skype-Benutzern kommunizieren** unter "Externer Zugriff".         |
|Sie möchten Ihren **Skype for Business Online-Benutzern** die Kommunikation mit **Skype for Business Online-Benutzern** in einer anderen Organisation und **Skype-Benutzern** innerhalb oder außerhalb Ihrer Organisation ermöglichen.    |Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Upgrademodus "Inseln" aus, um die Skype for Business-Benutzer in Ihrer Organisation zu unterstützen. <p>Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund".  <p> Aktivieren Sie die Einstellungen **Benutzer können mit Skype for Business- und Teams-Benutzern kommunizieren** und **Skype for Business-Benutzer können mit Skype-Benutzern kommunizieren** unter "Externer Zugriff". <p>Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen.       <p> **HINWEIS**: Der Administrator aus der anderen externen Domäne muss die Einstellung **Skype for Business-Benutzer können mit Skype-Benutzern kommunizieren** unter "Externer Zugriff" nicht aktivieren.|

> [!IMPORTANT]
> Sie müssen keine **"Skype-Domänen"** als zulässige Domänen hinzufügen, um es Microsoft Teams- oder Skype for Business Online-Benutzern zu ermöglichen, mit Skype-Benutzern innerhalb oder außerhalb Ihrer Organisation zu kommunizieren. Alle **Skype-Domänen** sind in der Whitelist enthalten, das heißt, alle diese Domänen werden als zulässig angesehen.

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-organization"></a>Microsoft Teams-Benutzern das Chatten und Kommunizieren mit Benutzern in einer anderen Organisation ermöglichen

Der externe Zugriff ermöglicht Ihren Microsoft Teams- und Skype for Business-Benutzern die Kommunikation mit anderen Benutzern außerhalb der Organisation. Standardmäßig kann Ihre Organisation mit allen externen Domänen kommunizieren. Wenn Sie blockierte Domänen hinzufügen, sind alle anderen Domänen zulässig, aber wenn Sie zulässige Domänen hinzufügen, werden alle anderen Domänen blockiert. Sie können den externen Zugriff für Ihre Organisation auf einfache Weise einrichten. Es gibt drei Szenarien für die Einrichtung:

- **Szenario 1**: Sie können **ÖFFENTLICHER VERBUND** verwenden. Dies ist die Standardeinstellung, mit der Personen in Ihrer Organisation Sie finden, anrufen und Ihnen Chatnachrichten senden sowie Besprechungen mit Personen außerhalb Ihrer Organisation einrichten können.

    Wenn Sie diese Konfiguration verwenden, können Ihre Benutzer mit ALLEN externen Domänen kommunizieren, die Microsoft Teams oder Skype for Business ausführen UND "Öffentlicher Verbund" verwenden oder Ihre Domäne zur Zulassungsliste hinzugefügt haben.

- **Szenario 2**: Sie können eine oder mehrere Domänen zur **ZULASSUNGSLISTE** hinzufügen. Klicken Sie dazu auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf **Erforderliche Aktion für diese Domäne**, und wählen Sie dann **Zulässig** aus. Beachten Sie dabei unbedingt, dass dadurch alle anderen Domänen **BLOCKIERT** werden.

- **Szenario 3**: Sie können eine oder mehrere Domänen zur **BLOCKIERUNGSLISTE** hinzufügen. Klicken Sie dazu auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf **Erforderliche Aktion für diese Domäne**, und wählen Sie dann **Blockiert** aus. Beachten Sie dabei unbedingt, dass dadurch alle anderen Domänen **ZUGELASSEN** werden.

Führen Sie diese Schritte aus, um Domänen zuzulassen oder zu blockieren.

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Schritt 1: Aktivieren Ihrer Organisation für die Kommunikation mit einer anderen Microsoft Teams-Organisation

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu **Organisationsweite Einstellungen** > **Externer Zugriff**.

2. Aktivieren Sie die Option **Benutzer können mit Skype for Business- und Teams-Benutzern kommunizieren**.

     ![Screenshot der aktivierten Option für den externen Zugriff](media/manage-external-access-2.png).

3. Wenn Sie allen Microsoft Teams-Organisationen die Kommunikation mit den Benutzern in Ihrer Organisation erlauben möchten, fahren Sie mit Schritt 5 fort.

4. Wenn Sie die Organisationen, die mit Benutzern in Ihrer Organisation kommunizieren können, einschränken möchten, können Sie entweder alle außer einigen bestimmten Domänen oder nur bestimmte Domänen zulassen. 

    - Wenn Sie alle außer einigen Domänen zulassen möchten, wählen Sie die zu blockierenden Domänen aus, indem Sie auf **Domäne hinzufügen** klicken. Geben Sie im Bereich **Domäne hinzufügen** den Domänennamen ein, klicken Sie auf **Blockiert** und dann auf **Fertig**. 
    - Wenn Sie die Kommunikation auf bestimmte Organisationen einschränken möchten, fügen Sie diese Domänen zur Liste mit dem Status **Zulässig** hinzu. Sobald Sie eine Domäne zur der Zulassungsliste hinzugefügt haben, wird die Kommunikationen mit anderen Organisationen auf die Organisationen beschränkt, die sich in der Zulassungsliste befinden. 

5. Klicken Sie auf **Speichern**.

6. Stellen Sie sicher, dass der Administrator in der andere Microsoft Teams-Organisation die gleichen Schritte ausführt. Ist in der anderen Organisation beispielsweise die Kommunikation mit Benutzern anderer Organisationen eingeschränkt, muss der Administrator der anderen Organisation die Domäne Ihres Unternehmens zur Liste der **zulässigen Domänen** hinzufügen.

### <a name="step-2---test-it"></a>Schritt 2: Testen

Um Ihr Setup zu testen, benötigen Sie einen Microsoft Teams-Benutzer, der sich nicht hinter der Firewall befindet.
  
1. Nachdem Sie und der Administrator der Organisation die Einstellungen für den **externen Zugriff** geändert haben, sollte es funktionieren.

2. Suchen Sie in der Teams-App anhand der E-Mail-Adresse nach der Person, und senden Sie eine Chatanfrage.

3. Bitten Sie Ihren Microsoft Teams-Kontakt, Ihnen eine Chatanfrage zu senden. Wenn Sie die Anfrage nicht erhalten, liegt das Problem bei den Einstellungen Ihrer Firewall (vorausgesetzt, Ihr Gegenüber hat die eigenen Firewalleinstellungen bereits überprüft).

4. Eine weitere Möglichkeit, um zu prüfen, ob das Problem bei Ihrer Firewall liegt, besteht darin, zu einem WLAN-Standort zu wechseln, der sich nicht hinter Ihrer Firewall befindet, z. B. zu einem Internet-Café, und Teams zu verwenden, um eine Chatanfrage an Ihren Kontakt zu senden. Wenn die Nachricht aus dem Internet-Café gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Kommunizieren mit Benutzern in einer Skype for Business Online-Organisation

Wenn Sie den externen Zugriff so einrichten, dass Ihre Microsoft Teams-Benutzer Benutzer in einer Skype for Business-Organisation mit eingeschränktem Zugriff finden und kontaktieren können, führen Sie die Schritte zum Einrichten des externen Zugriffs von Ihrer Domäne auf die Domäne der anderen Organisation aus. Bitten Sie den Administrator des anderen Unternehmens anschließend, die nachstehenden Schritte auszuführen, um den externen Zugriff für Skype for Business Online zu konfigurieren.

![Ein Symbol mit dem Skype for Business-Logo](media/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

Lassen Sie die folgenden Schritte vom Administrator in dieser Organisation durchführen:

1. Wechseln Sie im Microsoft 365 Admin Center zu **Admin Center** > **Teams & Skype** > **Altes Portal**.
  
2. Wählen Sie unter **Skype for Business Admin Center** die Option **Organisation** > **Externe Kommunikation** aus.

3. Um die Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne einzurichten, wählen Sie im Dropdownfeld **Nur für zulässige Domänen aktivieren**.

    ODER wählen Sie, wenn die Kommunikation mit allen anderen Unternehmen aktivieren werden soll, die über offene Skype for Business-Richtlinien verfügen, die Option **Aktivieren mit Ausnahme der blockierten Domänen** aus. Dies ist die Standardeinstellung.

4. Wählen Sie unter **Blockierte oder zulässige Domänen** die Option **+** aus, und fügen Sie den Namen der Domäne hinzu, die Sie zulassen möchten.

## <a name="related-topics"></a>Verwandte Themen

Informationen zum Gastzugriff in Microsoft Teams finden Sie unter [Verwalten des Gastzugriffs in Microsoft Teams](manage-guests.md).
