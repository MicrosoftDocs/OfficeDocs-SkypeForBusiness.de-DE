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
description: Ihr IT-Administrator kann den externen Zugriff für andere Domänen (Federation) konfigurieren, damit Benutzer aus diesen Domänen an Teams teilnehmen können.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 71aad6a5b19c1d641347b9e0f119acf2f72d5ce9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242129"
---
<a name="manage-external-access-in-microsoft-teams"></a>Verwalten des externen Zugriffs in Microsoft Teams
======================================================

Mit Microsoft Teams External Access können Teams-Benutzer aus anderen Domänen an ihren Chats und anrufen teilnehmen. Sie können auch externen Benutzern, die weiterhin Skype for Business Online, Skype for Business on-Prem oder sogar Skype nutzen, die Teilnahme erlauben.

Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:
  
- Sie verfügen über Benutzer in verschiedenen Domänen in Ihrem Unternehmen: beispielsweise Rob@contoso.com und Ann@northwindtraders.com.

- Sie möchten, dass die Personen in Ihrer Organisation Teams verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.

- Sie möchten, dass andere Personen in der Welt, die Teams verwenden, Ihre e-Mail-Adresse finden und mit Ihnen Kontakt aufnehmen können. Wenn Sie und ein anderer Benutzer den externen Zugriff aktivieren und die Domänen der anderen Personen zulassen, kann dies funktionieren. Wenn dies nicht funktioniert, sollte der andere Benutzer sicherstellen, dass seine Konfiguration Ihre Domäne nicht blockiert.

Externer Zugriff ermöglicht externen Benutzern das suchen, anrufen und Senden von Sofortnachrichten sowie das Einrichten von Besprechungen mit Ihnen. Wenn Sie jedoch möchten, dass externe Benutzer auf Teams und Kanäle zugreifen können, ist der Gastzugriff möglicherweise eine bessere Möglichkeit, um zu gehen. Weitere Informationen zu den Unterschieden zwischen dem externen Zugriff und dem Gastzugriff finden Sie unten unter [externer Zugriff vs. Gastzugriff](#external-access-vs-guest-access). Informationen zum Aktivieren des Gastzugriffs finden Sie unter [Aktivieren des Gastzugriffs](set-up-guests.md) , damit Benutzer kommunizieren können.

> [!IMPORTANT]
> Wenn Sie sich derzeit in der Microsoft Teams-APP an einen externen Benutzer außerhalb Ihrer Organisation, der derzeit kein Gast ihres Azure Active Directory (Azure AD) oder Mandanten ist, verbünden möchten, müssen Sie für Hybrid ordnungsgemäß eingerichtet sein und zu Skype for Business Online verschoben werden. Ab 2/25/2019 unterstützt Teams keine nativen Föderationen, ohne dass der Benutzer des SIP-Profils in Skype for Business Online verwaltet wird. Weitere Informationen zum Einrichten Ihres Kontos für Hybrid und anschließendes wechseln zu Teams finden Sie unter [Upgrade von Skype for Business-hybridbereitstellungen in Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="external-access-vs-guest-access"></a>Externer Zugriff vs. Gastzugriff

Der externe Zugriff (Föderation) und Gastzugriff unterscheiden sich von den folgenden:

- Gastzugriff gewährt einer einzelnen Person Zugriffsberechtigungen. Externer Zugriff gewährt einer gesamten Domäne Zugriffsberechtigungen.

- Der Gastzugriff, nachdem er von einem Teambesitzer gewährt wurde, ermöglicht es einem Gast, auf [Ressourcen](guest-experience.md)wie Kanal Diskussionen und Dateien für ein bestimmtes Team zuzugreifen und mit anderen Benutzern in dem Team zu chatten, zu dem Sie eingeladen wurden. Beim externen Zugriff (Federated-Chat) haben die Teilnehmer des externen Chats keinen Zugriff auf die Teams oder Teamressourcen der einladenden Organisation. Sie können nur an einem einzigen Partner-Chat teilnehmen. Mandantenadministratoren können zwischen den beiden Kommunikationsoptionen wählen, je nachdem, welche Ebene der Zusammenarbeit für die externe Partei erwünscht ist. Administratoren können je nach Ihren organisatorischen Anforderungen entweder Ansätze oder beides auswählen, aber wir empfehlen, den Gastzugriff für eine umfassendere, kollaborative Teams-Erfahrung zu aktivieren. 

In der folgenden Tabelle finden Sie eine Übersicht über die Features für den externen und den Gastzugriff.

| Feature | Benutzer für externen Zugriff | Gastzugriff-Benutzer |
|---------|-----------------------|--------------------|
| Der Benutzer kann mit jemandem in einem anderen Unternehmen chatten. | Ja |Ja |
| Der Benutzer kann jemanden in einem anderen Unternehmen anrufen | Ja | Ja |
| Der Benutzer kann sehen, ob jemand aus einem anderen Unternehmen für Anrufe oder Chats zur Verfügung steht. | Ja | Ja<sup>1</sup> |
| Benutzer kann über externe Mandanten nach Benutzern suchen | Ja<sup>2</sup> | Nein |
| Benutzer kann Dateien freigeben | Nein | Ja |
| Benutzer kann auf Teamressourcen zugreifen | Nein | Ja |
| Benutzer kann zu einem Gruppen-Chat hinzugefügt werden | Nein | Ja |
| Benutzer kann zu einer Besprechung hinzugefügt werden | Ja | Ja |
| Zusätzliche Benutzer können einem Chat mit einem externen Benutzer hinzugefügt werden. | Nr.<sup>3</sup> | Nicht zutreffend |
| Der Benutzer wird als externer Partner identifiziert | Ja | Ja |
| Anwesenheit wird angezeigt | Ja | Ja |
| Abwesenheitsnachricht wird angezeigt | Nein | Ja |
| Der einzelne Benutzer kann blockiert werden. | Nein | Ja |
| @Mentions werden unterstützt | Nein | Ja |
| Private Anrufe tätigen | Ja | Ja |
| IP-Video zulassen | Ja | Ja |
| Bildschirmfreigabe Modus | Nein | Ja |
| Sofortbesprechung zulassen | Nein | Ja |
| Bearbeiten von gesendeten Nachrichten | Nein | Ja |
| Kann gesendete Nachrichten löschen | Nein | Ja |
| Verwenden von Giphy in einer Unterhaltung | Nein | Ja |
| Verwenden von Memen in einer Unterhaltung | Nein | Ja |
| Verwenden von Aufklebern in einer Unterhaltung | Nein | Ja |
||||

<sup>1</sup> vorausgesetzt, dass der Benutzer als Gast hinzugefügt wurde und als Gast für den Gast Mandanten angemeldet ist.<br>
<sup>2</sup> nur per e-Mail oder SIP-Adresse (Session Initiation Protocol).<br>
<sup>3</sup> externer Chat (Federated) ist nur 1:1.

Weitere Informationen zu Gast Features und der Gast Erfahrung finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) und [der Art der Gast Erfahrung](https://docs.microsoft.com/microsoftteams/guest-experience).

Weitere Informationen zur kostenlosen Version von Teams und deren Funktionsweise mit Features, die im externen Zugriff gefunden werden, finden Sie unter [Unterschiede zwischen Microsoft Teams und Microsoft Teams kostenlos](https://support.office.com/article/differences-between-microsoft-teams-and-microsoft-teams-free-0b69cf39-eb52-49af-b255-60d46fdf8a9c?ui=en-US&rs=en-US&ad=US).

## <a name="quick-steps-for-scenarios"></a>Schnelle Schritte für Szenarien

|**Sie möchten....**  |**Schnelle Schritte**  |
|---------|-----------------------|
|Sie möchten, dass **Teams-Benutzer** in Ihrer Organisation mit **Teams-Benutzern** in einer anderen (externen) Organisation kommunizieren können.|Fügen Sie in externer Zugriff die externe Domäne zur Liste der zulässigen Listen hinzu, oder verwenden Sie Open Federation. <p>Führen Sie dann den Administrator in der anderen Teams-Organisation aus.      |
|Sie möchten, dass **Teams-Benutzer** in Ihrer Organisation mit **Skype for Business Online-Benutzern** in derselben Organisation kommunizieren können.  |Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Aktualisierungsmodus für Inseln aus, um Skype for Business-Benutzer in Ihrer Organisation zu unterstützen.   |
|Sie möchten, dass **Teams-Benutzer** in Ihrer Organisation mit **Skype for Business Online-Benutzern** in einer anderen (externen) Organisation kommunizieren können.      |Fügen Sie in externer Zugriff die externe Domäne zur Liste der zulässigen Listen hinzu, oder verwenden Sie Open Federation.  <p>Aktivieren Sie **Benutzer können mit Skype for Business-und Teams-Benutzern** im externen Zugriff kommunizieren. <p>Führen Sie dann den Administrator in der anderen Teams-Organisation aus. <p>**Hinweis**: die externe Domäne mit Skype for Business-Benutzern muss den Koexistenzmodus aktivieren oder den Inseln-Upgrademodus auswählen, um Skype for Business-Benutzer in dieser Organisation zu unterstützen.|
|Sie möchten, dass **Teams-Benutzer** in Ihrer Organisation mit **Skype** -Benutzern von innerhalb oder außerhalb Ihrer Organisation aus kommunizieren können.   | Derzeit kein unterstütztes Szenario. <p>**Wichtig**: Ihre Teams-Benutzer können nicht mit Skype-Nutzern kommunizieren, aber Ihre Skype for Business-Benutzer in Ihrer Organisation können mit Skype-Nutzern innerhalb oder außerhalb Ihrer Organisation kommunizieren, wenn diese beiden Voraussetzungen erfüllt sind: <p>1) aktivieren Sie **Benutzer können mit Skype for Business kommunizieren, und Teams Benutzer** und **Skype for Business-Benutzer können mit den Skype-Benutzer** Einstellungen im externen Zugriff kommunizieren. <p> 2) Ihre Organisation läuft im Koexistenzmodus. |
|Sie möchten, dass die **Benutzer Ihrer Teams** mit **Skype for Business Online-Benutzern** aus einer lokalen Organisation und mit **Skype-Nutzern**kommunizieren können.   |Fügen Sie in externer Zugriff die externe Domäne zur Liste der zulässigen Listen hinzu, oder verwenden Sie Open Federation. . <p>Aktivieren Sie **Benutzer können mit Skype for Business-und Teams-Benutzern** im externen Zugriff kommunizieren. <p>Aktivieren von **Skype for Business-Benutzern können mit den Skype-Benutzern** im externen Zugriff kommunizieren. <p> Führen Sie dann den Administrator in der lokalen Organisation aus.<p>**Wichtig** In diesem Szenario können Ihre Teams-Benutzer nicht mit Skype-Nutzern kommunizieren, aber Skype for Business-Benutzer in Ihrer Organisation können mit Skype-Benutzern innerhalb oder außerhalb Ihrer Organisation kommunizieren, wenn Sie **Benutzer mit Skype for Business kommunizieren können. und Teams-Benutzer** und **Skype for Business-Benutzer können mit den Skype-Benutzer** Einstellungen im externen Zugriff kommunizieren.|
|Sie möchten, dass Ihre **Skype for Business Online-Benutzer** mit **Teams-Benutzern** in einer anderen Office 365-Organisation kommunizieren können.|Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Aktualisierungsmodus für Inseln aus, um Skype for Business-Benutzer in Ihrer Organisation zu unterstützen. <p>Fügen Sie in externer Zugriff die externe Domäne zur Liste der zulässigen Listen hinzu, oder verwenden Sie Open Federation.  <p> Aktivieren Sie **Benutzer können mit Skype for Business-und Teams-Benutzern** im externen Zugriff kommunizieren. <p>Lassen Sie den Administrator in der anderen Teams-Organisation die gleichen Schritte ausführen. |
|Sie möchten, dass Ihre **Skype for Business Online-Benutzer** mit den **Skype for Business Online-Benutzern** aus einer anderen Office 365-Organisation kommunizieren können.    | Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Aktualisierungsmodus für Inseln aus, um Skype for Business-Benutzer in Ihrer Organisation zu unterstützen. <p>Fügen Sie in externer Zugriff die externe Domäne zur Liste der zulässigen Listen hinzu, oder verwenden Sie Open Federation. <p> Aktivieren Sie **Benutzer können mit Skype for Business-und Teams-Benutzern** im externen Zugriff kommunizieren.<p>Führen Sie dann den Administrator in der anderen Teams-Organisation aus, um dieselben Aufgaben auszuführen. |
|Sie möchten, dass Ihre **Skype for Business Online-Benutzer** mit den **Skype for Business Online-Benutzern** von einer lokalen Organisation aus kommunizieren können.     |Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Aktualisierungsmodus für Inseln aus, um Skype for Business-Benutzer in Ihrer Organisation zu unterstützen. <p>Fügen Sie in externer Zugriff die externe Domäne zur Liste der zulässigen Listen hinzu, oder verwenden Sie Open Federation.  <p>Aktivieren Sie **Benutzer können mit Skype for Business-und Teams-Benutzern** im externen Zugriff kommunizieren.  <p> Lassen Sie den Administrator in der lokalen Organisation die gleichen Schritte ausführen. |
|Sie möchten, dass Ihre **Skype for Business Online-Benutzer** mit **Skype-Nutzern** (innerhalb oder außerhalb Ihrer Organisation) kommunizieren können.   |Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Aktualisierungsmodus für Inseln aus, um Skype for Business-Benutzer in Ihrer Organisation zu unterstützen. <p>Aktivieren Sie **Skype for Business-Benutzer können mit Skype-Benutzern** in externen Zugriffen kommunizieren.         |
|Sie möchten, dass Ihre **Skype for Business Online-Benutzer** mit **Skype for Business Online-Benutzern** in einer anderen Organisation und **Skype-Benutzern** von innerhalb oder außerhalb Ihrer Organisation kommunizieren können.    |Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Aktualisierungsmodus für Inseln aus, um Skype for Business-Benutzer in Ihrer Organisation zu unterstützen. <p>Fügen Sie in externer Zugriff die externe Domäne zur Liste der zulässigen Listen hinzu, oder verwenden Sie Open Federation.  <p> Aktivieren Sie **Benutzer können mit Skype for Business-und Teams-Benutzern kommunizieren** , und die **Skype for Business-Benutzer können mit Skype-Benutzern** im externen Zugriff kommunizieren. <p>Lassen Sie den Administrator in der anderen Teams-Organisation die gleichen Schritte ausführen.       <p> **Hinweis**: der Administrator aus der anderen externen Domäne muss keine **Skype for Business-Benutzer** aktivieren, die mit Skype-Benutzern in externen Zugriffen kommunizieren können.|

> [!IMPORTANT]
> Sie müssen keine **"Skype-Domänen"** als zugelassene Domänen hinzufügen, um Teams oder Skype for Business Online-Benutzern die Kommunikation mit Skype-Nutzern innerhalb oder außerhalb Ihrer Organisation zu ermöglichen. Alle **Skype-Domains** sind whitelisted, was bedeutet, dass alle diese Domains als erlaubt gelten.

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-organization"></a>Zulassen, dass Ihre Teams-Benutzer chatten und mit Benutzern in einer anderen Organisation kommunizieren

Externer Zugriff ermöglicht es ihren Teams und Skype for Business-Benutzern, mit anderen Benutzern zu kommunizieren, die sich außerhalb Ihrer Organisation befinden. Standardmäßig kann Ihre Organisation mit allen externen Domänen kommunizieren. Wenn Sie Blockierte Domänen hinzufügen, werden alle anderen Domänen zugelassen, aber wenn Sie zulässige Domänen hinzufügen, werden alle anderen Domänen blockiert. Sie können ganz einfach externen Zugriff für Ihre Organisation einrichten. Es gibt drei Szenarien für die Einrichtung:

- **Szenario 1** : Sie können **Open Federation**verwenden. Dies ist die Standardeinstellung, mit der Personen in Ihrer Organisation Chatnachrichten/-Chats suchen, anrufen und senden sowie Besprechungen mit Personen einrichten können, die sich außerhalb Ihrer Organisation befinden.

    Wenn Sie diese Einrichtung verwenden, können Ihre Benutzer mit allen externen Domänen kommunizieren, in denen Teams oder Skype for Business ausgeführt wird und die offene Föderation verwenden oder Ihre Domäne zur Zulassungsliste hinzugefügt haben.

- **Szenario 2** – Sie können eine Domäne oder Domänen zur **Zulassungs** Liste hinzufügen. Klicken Sie dazu auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf Aktion, die für **diese Domäne ausgeführt werden soll**, und wählen Sie dann **zulässig**aus. Wenn Sie dies tun, ist es wichtig zu wissen, dass alle anderen Domänen **blockiert** werden.

- **Szenario 3** : Sie können eine Domäne oder Domänen zur **Sperr** Liste hinzufügen. Klicken Sie dazu auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf **Aktion, um diese Domäne zu übernehmen**, und wählen Sie dann **blockiert**aus. Wenn Sie dies tun, ist es wichtig zu wissen, dass alle anderen Domänen **zugelassen** werden.

Führen Sie die folgenden Schritte aus, um Domänen zuzulassen oder zu blockieren.

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Schritt 1 – Aktivieren Ihrer Organisation für die Kommunikation mit einer anderen Teams-Organisation

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png)-Logo**mit dem Microsoft Teams Admin Center** zeigt  

1. Navigieren Sie in der linken Navigationsleiste zu **organisationsweiten Einstellungen** > **externer Zugriff**.

2. Schalten Sie die **Benutzer können mit Skype for Business kommunizieren und die Benutzer von Teams** wechseln zu **ein**.

     ![Screenshot des aktivierten externen Zugriffs Schalters](media/manage-external-access-2.png).

3. Wenn Sie zulassen möchten, dass alle Teams-Organisationen mit Benutzern in Ihrer Organisation kommunizieren, fahren Sie mit Schritt 5 fort.

4. Wenn Sie die Organisationen einschränken möchten, die mit Benutzern in Ihrer Organisation kommunizieren können, können Sie entweder alle außer einigen Domänen zulassen, oder Sie können nur bestimmte Domänen zulassen. 

    - Wenn Sie alle außer einigen Domänen zulassen möchten, fügen Sie die zu blockierenden Domänen hinzu, indem Sie auf **Domäne hinzufügen**klicken. Geben Sie im Bereich **Domäne hinzufügen** den Domänennamen ein, klicken Sie auf **blockiert**, und klicken Sie dann auf Clik **Fertig**. 
    - Wenn Sie die Kommunikation auf bestimmte Organisationen einschränken möchten, fügen Sie diese Domänen der Liste mit dem Status **zulässig**hinzu. Nachdem Sie der Zulassungsliste eine beliebige Domäne hinzugefügt haben, sind die Kommunikation mit anderen Organisationen nur auf die Organisationen limitiert, deren Domänen sich in der Zulassungsliste befinden. 

5. Klicken Sie auf **Speichern**.

6. Stellen Sie sicher, dass der Administrator in der anderen Teams-Organisation die gleichen Schritte ausführt. In der Liste **zugelassene Domänen** muss der Administrator beispielsweise die Domäne für Ihr Unternehmen eingeben, wenn er die Organisationen beschränkt, die mit seinen Benutzern kommunizieren können.

### <a name="step-2---test-it"></a>Schritt 2 – testen

Um Ihr Setup zu testen, benötigen Sie einen Teams-Benutzer, der sich nicht hinter Ihrer Firewall befindet.
  
1. Nachdem Sie und der Administrator des Unternehmens die Einstellungen für den **externen Zugriff** geändert haben, sollten Sie gut gehen.

2. Suchen Sie in der Teams-App nach der e-Mail-Adresse der Person, und senden Sie eine Anfrage an den Chat.

3. Bitten Sie Ihren Team-Kontakt, Ihnen eine Anfrage zum Chat zu senden. Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).

4. Eine weitere Möglichkeit, zu testen, ob das Problem Ihre Firewall ist, besteht darin, zu einem WLAN-Standort zu wechseln, der sich nicht hinter Ihrer Firewall befindet. wie ein Coffee-Shop, und verwenden Sie Teams, um eine Anfrage an Ihren Kontakt zu senden, um zu chatten. Wenn die Nachricht am WLAN-Standort durchläuft, aber nicht, wenn Sie bei der Arbeit sind, wissen Sie, dass das Problem Ihre Firewall ist.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Kommunizieren mit Benutzern in einer Skype for Business Online-Organisation

Wenn Sie den externen Zugriff einrichten, damit die Benutzer Ihrer Teams Benutzer in einer Skype for Business-Organisation finden und kontaktieren können, die die Kontaktaufnahme mit ihren Benutzern einschränken, führen Sie die Schritte aus, um den externen Zugriff von Ihrer Domäne auf die Domäne der anderen Organisation einzurichten. Bitten Sie den Administrator in der anderen Organisation, die folgenden Schritte auszuführen, um den externen Zugriff für Skype for Business Online zu konfigurieren.

![Ein Symbol mit dem Skype for Business-](media/sfb-logo-30x30.png) Logo **im Skype for Business Admin Center**

Führen Sie den Administrator in dieser Organisation aus, um die folgenden Schritte auszuführen:

1. Wechseln Sie im Microsoft 365 Admin Center zu **Admin Center** > **Teams #a0 Skype** > **Legacy-Portal**.
  
2. Wählen Sie im **Skype for Business Admin Center**die Option **Organisation** > **External Communications**aus.

3. Um die Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne einzurichten, wählen Sie im Dropdownfeld **nur für zulässige Domänen**aktivieren aus.

    Wenn Sie die Kommunikation mit allen anderen Personen in der Welt ermöglichen möchten, die Skype for Business-Richtlinien geöffnet haben, wählen Sie **ein, außer für blockierte Domänen**. Dies ist die Standardeinstellung.

4. Wählen Sie unter **blockierte oder zulässige Domänen**die Option **+** aus, und fügen Sie dann den Namen der Domäne hinzu, die Sie zulassen möchten.

## <a name="related-topics"></a>Verwandte Themen

Informationen zum Gastzugriff in Microsoft Teams finden Sie unter [Verwalten des Gastzugriffs in Microsoft Teams](manage-guests.md).
