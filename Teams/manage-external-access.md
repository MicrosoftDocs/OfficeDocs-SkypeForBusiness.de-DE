---
title: Verwaltung des externen Zugriffs (Verbund) in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
description: Ihre Teams oder IT-Administratoren können den externen Zugriff für andere Domänen (Föderationen) so konfigurieren, dass Benutzer aus diesen Domänen an Teams teilnehmen können.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: eb0b252f2df1deb3e2a92bfada9a04b1df561316
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836895"
---
<a name="manage-external-access-in-microsoft-teams"></a>Verwaltung des externen Zugriffs in Microsoft Teams
======================================================

Externer Zugriff ist eine Möglichkeit für externe Teams-Benutzer aus einer ganzen Domäne, Besprechungen mit Ihnen in Teams zu finden, anzurufen, zu chatten und einzurichten. Sie können auch externen Zugriff verwenden, um mit externen Benutzern zu kommunizieren, die weiterhin Skype for Business (Online und lokal) und Skype (in den frühen 2020) verwenden.

Wenn Sie externen Benutzern hingegen den Zugriff auf Teams und Kanäle gewähren möchten, ist der Gastzugriff möglicherweise besser geeignet. Weitere Informationen zu den Unterschieden zwischen externem Zugriff und Gastzugriff finden Sie unter [Vergleichen von externem und Gastzugriff](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Verwenden Sie den externen Zugriff in folgenden Fällen:
  
- Sie verfügen über Benutzer in verschiedenen Domänen, die zusammenarbeiten müssen. Beispielsweise arbeiten Rob@contoso.com und Ann@northwindtraders.com zusammen mit einigen anderen Benutzern in den Domänen contoso.com und northwindtraders.com an einem Projekt.

- Sie möchten den Personen in Ihrer Organisation die Möglichkeit geben, Microsoft Teams zu verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.

- Sie möchten, dass alle anderen Microsoft Teams-Benutzer aus aller Welt Sie anhand Ihrer E-Mail-Adresse finden und Kontakt zu Ihnen aufnehmen können. 




> [!IMPORTANT]
> Um innerhalb der Microsoft Teams-App einen Verbund mit einem externen Benutzer außerhalb Ihrer Organisation zu erstellen, der derzeit kein Gastbenutzer in Azure Active Directory (Azure AD) oder Mandant ist, müssen Sie ordnungsgemäß für Hybridumgebungen konfiguriert und bereits auf Skype for Business Online umgestiegen sein. Ab dem 25. Februar 2019 unterstützt Teams keine nativen Föderationen, ohne dass der Nutzer des SIP-Profils in Skype for Business Online verwaltet wird. Weitere Informationen dazu, wie Sie Ihr Konto für die Hybridumgebung einrichten und dann zu Teams wechseln, finden Sie unter [Upgrade von einer Skype for Business-Hybridbereitstellung zu Microsoft Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).






## <a name="plan-for-external-access"></a>Planen des externen Zugriffs

Standardmäßig ist der externe Zugriff in Teams aktiviert, was bedeutet, dass Ihre Organisation mit allen externen Domänen kommunizieren kann. Wenn Sie Blockierte Domänen hinzufügen, werden alle anderen Domänen zugelassen. und wenn Sie zulässige Domänen hinzufügen, werden alle anderen Domänen blockiert. Es gibt drei Szenarien für das Einrichten des externen Zugriffs im Team Admin Center (**organisationsweite Einstellungen** > **externer Zugriff**):

- **Föderation öffnen**: Dies ist die Standardeinstellung in Teams und ermöglicht es Personen in Ihrer Organisation, Besprechungen mit Personen außerhalb Ihrer Organisation in einer beliebigen Domäne zu finden, anzurufen, zu chatten und einzurichten.

    In diesem Szenario können Ihre Benutzer mit allen externen Domänen kommunizieren, auf denen Teams oder Skype for Business ausgeführt wird und die Open Federation verwenden oder Ihre Domäne zur Zulassungsliste hinzugefügt haben.

- **Zulassen bestimmter Domänen**: durch Hinzufügen von Domänen zu einer **Zulassungs** Liste beschränken Sie den externen Zugriff auf die zulässigen Domänen. Nachdem Sie eine Liste der zulässigen Domänen eingerichtet haben, werden alle anderen Domänen blockiert. Wenn Sie bestimmte Domänen zulassen möchten, klicken Sie auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf Aktion, die für **diese Domäne ausgeführt werden soll**, und wählen Sie dann **zulässig**aus.

- **Blockieren bestimmter Domänen** – durch Hinzufügen von Domänen zu einer **Sperr** Liste können Sie mit allen externen Domänen mit *Ausnahme* der blockierten Personen kommunizieren. Wenn Sie bestimmte Domänen blockieren möchten, klicken Sie auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf **Aktion, um diese Domäne zu übernehmen**, und wählen Sie dann **blockiert**aus. Nachdem Sie eine Liste der blockierten Domänen eingerichtet haben, werden alle anderen Domänen zugelassen.

## <a name="allow-or-block-domains"></a>Zulassen oder Blockieren von Domänen

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

4. Eine weitere Möglichkeit, zu testen, ob das Problem Ihre Firewall ist, besteht darin, zu einem WLAN-Standort zu wechseln, der sich nicht hinter Ihrer Firewall befindet. z. B. zu einem Internet-Café, und Teams zu verwenden, um eine Chatanfrage an Ihren Kontakt zu senden. Wenn die Nachricht am WLAN-Standort durchläuft, aber nicht, wenn Sie bei der Arbeit sind, wissen Sie, dass das Problem Ihre Firewall ist.

> [!NOTE]
> Wenn Sie und ein anderer Benutzer sowohl den externen Zugriff aktivieren als auch die Domänen eines anderen Benutzers zulassen, kann dies funktionieren. Wenn dies nicht funktioniert, sollte der andere Benutzer sicherstellen, dass seine Konfiguration Ihre Domäne nicht blockiert.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Kommunizieren mit Benutzern in einer Skype for Business Online-Organisation

Wenn Sie den externen Zugriff einrichten, damit die Benutzer Ihrer Teams in einer Skype for Business-Organisation Benutzer finden und kontaktieren können, die die Kontaktaufnahme mit ihren Benutzern einschränken, führen Sie die Schritte aus, um den externen Zugriff von Ihrer Domäne auf die Domäne der anderen Organisation einzurichten. Bitten Sie den Administrator des anderen Unternehmens anschließend, die nachstehenden Schritte auszuführen, um den externen Zugriff für Skype for Business Online zu konfigurieren. 

Spezifische Anleitungen zu gängigen Skype for Business Online-Szenarien finden Sie unten unter [häufige Szenarien für den externen Zugriff](#common-external-access-scenarios) .

![Ein Symbol mit dem Skype for Business-Logo](media/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

Lassen Sie die folgenden Schritte vom Administrator in dieser Organisation durchführen:

1. Wechseln Sie im Microsoft 365 Admin Center zu **Admin Center** > **Teams & Skype** > **Altes Portal**.
  
2. Wählen Sie unter **Skype for Business Admin Center** die Option **Organisation** > **Externe Kommunikation** aus.

3. Um die Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne einzurichten, wählen Sie im Dropdownfeld **Nur für zulässige Domänen aktivieren**.

    ODER wählen Sie, wenn die Kommunikation mit allen anderen Unternehmen aktivieren werden soll, die über offene Skype for Business-Richtlinien verfügen, die Option **Aktivieren mit Ausnahme der blockierten Domänen** aus. Dies ist die Standardeinstellung.

4. Wählen Sie unter **Blockierte oder zulässige Domänen** die Option **+** aus, und fügen Sie den Namen der Domäne hinzu, die Sie zulassen möchten.

## <a name="common-external-access-scenarios"></a>Allgemeine Szenarien für den externen Zugriff

|**Wenn Sie möchten....**  |**Tun Sie dies**  |
|---------|-----------------------|
|Lassen Sie die **Teams-Benutzer** in Ihrer Organisation mit **Teams-Benutzern** in einer anderen (externen) Organisation kommunizieren.|Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund". Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen.      |
|Lassen Sie die **Team Benutzer** in Ihrer Organisation mit **Skype for Business Online-Benutzern** in der gleichen Organisation kommunizieren.  |Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Upgrademodus "Inseln" aus, um die Skype for Business-Benutzer in Ihrer Organisation zu unterstützen.   |
|Lassen Sie die **Team Benutzer** in Ihrer Organisation mit **Skype for Business Online-Benutzern** in einer anderen (externen) Organisation kommunizieren.      |Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund". <br><br>Aktivieren Sie die Einstellung **Benutzer können mit Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff". Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen. <br><br>**HINWEIS**: In der externen Domäne mit Skype for Business-Benutzern muss der Koexistenzmodus aktiviert oder der Upgrademodus "Inseln" ausgewählt werden, um die Skype for Business-Benutzer in dieser Organisation zu unterstützen.|
|Lassen Sie **Teams-Benutzer** in Ihrer Organisation mit **Skype** -Benutzern von innerhalb oder außerhalb Ihrer Organisation kommunizieren.   | Dieses Szenario wird in Kürze verfügbar sein. <br><br>**Wichtig**: Ihre Teams-Nutzer können noch nicht mit Skype-Nutzern kommunizieren, aber Ihre Skype for Business-Nutzer können mit Skype-Nutzern innerhalb oder außerhalb Ihrer Organisation weiterhin kommunizieren. Aktivieren Sie die **Benutzer können mit Skype for Business kommunizieren, und Teams Benutzer** und **Skype for Business-Benutzer können mit den Skype-Benutzer** Einstellungen im externen Zugriff kommunizieren. |
|Lassen Sie Ihre **Skype for Business Online-Benutzer** mit **Teams-Benutzern** in einer anderen Office 365-Organisation kommunizieren.| Ihre Skype for Business Online-Benutzer können mit den Teams-Benutzern in einer anderen Organisation kommunizieren, wenn sich die Benutzer in einem der folgenden Aktualisierungsmodi befinden: Inseln, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; und die Team Benutzer der anderen Organisation befinden sich im TeamsOnly-Modus. <br><br>Aktivieren Sie die Option **Benutzer können mit Skype for Business-und Teams-Benutzern** im externen Zugriff kommunizieren. Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen.|
|Lassen Sie Ihre **Skype for Business Online-Benutzer** mit **Skype for Business Online-Benutzern** aus einer anderen Office 365-Organisation kommunizieren.    | Ihre Skype for Business Online-Benutzer können mit Skype for Business Online-Benutzern in einer anderen Organisation kommunizieren, wenn sich die Benutzer in einem der folgenden Aktualisierungsmodi befinden: Inseln, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; und die Skype for Business Online-Benutzer der anderen Organisation befinden sich in einem der folgenden Upgrade-Modi: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Aktivieren Sie die Option **Benutzer können mit Skype for Business-und Teams-Benutzern** im externen Zugriff kommunizieren. Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen.|
|Lassen Sie Ihre **Skype for Business Online-Benutzer** mit **Skype for Business-Benutzern** aus einer lokalen Organisation kommunizieren.     |Ihre Skype for Business Online-Benutzer können mit Skype for Business-Benutzern von einer lokalen Organisation aus kommunizieren, wenn sich die Benutzer in einem der folgenden Aktualisierungsmodi befinden: Inseln, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; und die Skype for Business Online-Benutzer der anderen Organisation befinden sich in einem der folgenden Upgrade-Modi: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Aktivieren Sie die Option **Benutzer können mit Skype for Business-und Teams-Benutzern** im externen Zugriff kommunizieren. Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen.|
|Lassen Sie Ihre **Skype for Business Online-Benutzer** mit **Skype-Nutzern** (innerhalb oder außerhalb Ihrer Organisation) kommunizieren.   |Aktivieren Sie die Einstellung **Skype for Business-Benutzer können mit Skype-Benutzern kommunizieren** unter "Externer Zugriff".|

> [!IMPORTANT]
> Sie müssen keine **Skype-Domänen** als zulässige Domänen hinzufügen, um Teams oder Skype for Business Online-Benutzern die Kommunikation mit Skype-Nutzern innerhalb oder außerhalb Ihrer Organisation zu ermöglichen. Alle **Skype-Domains** sind in Whitelists, was bedeutet, dass alle diese Domains als erlaubt gelten.



## <a name="how-does-external-access-compare-with-guest-access"></a>Wie vergleicht sich externer Zugriff mit Gastzugriff?

Wenn Sie mehr über den Unterschied zwischen dem externen Zugriff und dem Gastzugriff erfahren möchten, lesen Sie [kommunizieren mit Benutzern aus anderen Organisationen](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Verwandte Themen

[Natives Chat-Erlebnis für externe (Federated-) Benutzer](native-chat-for-external-users.md)
