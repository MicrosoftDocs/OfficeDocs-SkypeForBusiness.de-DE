---
title: Verwalten des externen Zugriffs (Föderation)
author: SerdarSoysal
ms.author: serdars
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
- seo-marvel-mar2020
description: Ihr Teams- oder IT-Administrator kann den externen Zugriff für andere Domänen (Verbund) so konfigurieren, dass Benutzer aus diesen Domänen in Teams teilnehmen können.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: b3d6eafe5f2ab5989e5b21a060901dc317332127
ms.sourcegitcommit: c1aaf1f81c07c0956095b5bd4cb241b1de67b189
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2020
ms.locfileid: "46897825"
---
<a name="manage-external-access-in-microsoft-teams"></a>Verwaltung des externen Zugriffs in Microsoft Teams
======================================================

Externer Zugriff ist eine Möglichkeit für Teams-Benutzer aus einer ganzen externen Domäne Sie zu finden, anrufen, mit Ihnen zu chatten und Besprechungen mit Ihnen in Teams einzurichten. Über einen externen Zugang können Sie auch mit externen Benutzern kommunizieren, die noch Skype for Business (online oder lokal) bzw. Skype (in der Vorschau) verwenden.

Wenn Sie externen Benutzern hingegen den Zugriff auf Teams und Kanäle gewähren möchten, ist der Gastzugriff möglicherweise besser geeignet. Weitere Informationen zu den Unterschieden zwischen externem Zugriff und Gastzugriff finden Sie unter [Vergleich von externem Zugriff und Gastzugriff](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Verwenden Sie den externen Zugriff in folgenden Situationen:
  
- Sie verfügen über Benutzer in unterschiedlichen Domänen, die zusammenarbeiten müssen. Beispielsweise arbeiten Rob@contoso.com und Ann@northwindtraders.com gemeinsam mit einigen anderen in den Domänen contoso.com und northwindtraders.com an einem Projekt.

- Sie möchten den Personen in Ihrer Organisation die Möglichkeit geben, Microsoft Teams zu verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.

- Sie möchten, dass alle anderen Microsoft Teams-Benutzer aus aller Welt Sie anhand Ihrer E-Mail-Adresse finden und Kontakt zu Ihnen aufnehmen können. 

> [!IMPORTANT]
> Um innerhalb der Microsoft Teams-App einen Verbund mit einem externen Benutzer außerhalb Ihrer Organisation zu erstellen, der derzeit kein Gastbenutzer in Azure Active Directory (Azure AD) oder Mandant ist, müssen Sie ordnungsgemäß für Hybridumgebungen konfiguriert und bereits auf Skype for Business Online umgestiegen sein. Ab dem 25. Februar 2019 unterstützt Teams keine **nativen** Föderationen, ohne dass der Nutzer des SIP-Profils in Skype for Business Online verwaltet wird. Weitere Informationen dazu, wie Sie Ihr Konto für die Hybridumgebung einrichten und dann zu Teams wechseln, finden Sie unter [Upgrade von einer Skype for Business-Hybridbereitstellung zu Microsoft Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="plan-for-external-access"></a>Plan für externen Zugriff

Der externe Zugriff ist in Teams standardmäßig aktiviert. Das bedeutet, dass Ihre Organisation mit allen externen Domänen kommunizieren kann. Wenn Sie blockierte Domänen hinzufügen, sind alle anderen Domänen zulässig, und wenn Sie zulässige Domänen hinzufügen, werden alle anderen Domänen blockiert. Es gibt drei Szenarien für das Einrichten des externen Zugriffs im Microsoft Teams Admin Center (**Organisationsweite Einstellungen** > **Externer Zugriff**):

- **Offener Verbund**: Dies ist die Standardeinstellung in Teams, mit der Personen in Ihrer Organisation Sie finden, anrufen, mit Ihnen chatten und Besprechungen mit Personen in einer beliebigen Domäne außerhalb Ihrer Organisation einrichten können.

    In diesem Szenario können Ihre Benutzer mit allen externen Domänen kommunizieren, die Microsoft Teams oder Skype for Business ausführen UND den öffentlichen Verbund verwenden ODER Ihre Domäne zur Zulassungsliste hinzugefügt haben.

- **Bestimmte Domänen zulassen**: Indem Sie Domänen zu einer **Zulassungsliste** hinzufügen, beschränken Sie den externen Zugriff auf die erlaubten Domänen. Sobald Sie eine Liste der erlaubten Domänen eingerichtet haben, werden alle anderen Domänen gesperrt. Um bestimmte Domänen zuzulassen, klicken Sie auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf **Erforderliche Aktion für diese Domäne**, und wählen Sie dann **Zulässig** aus.

- **Bestimmte Domänen blockieren**: Indem Sie Domänen zu einer **Sperrliste** hinzufügen, können Sie mit allen externen Domänen* außer* den blockierten Domänen kommunizieren. Um bestimmte Domänen zu blockieren, klicken Sie auf **Domäne hinzufügen**, fügen Sie den Domänennamen hinzu, klicken Sie auf **Erforderliche Aktion für diese Domäne**, und wählen Sie dann **Blockiert** aus. Sobald Sie eine Liste blockierter Domänen erstellt haben, werden alle anderen Domänen zugelassen.

## <a name="allow-or-block-domains"></a>Zulassen oder Blockieren von Domänen

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>Schritt 1 – Aktivieren Ihrer Organisation für die Kommunikation mit anderen Teams oder Skype for Business-Organisationen

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu **Organisationsweite Einstellungen** > **Externer Zugriff**.

2. Aktivieren Sie die Option **Benutzer können mit anderen Skype for Business- und Teams-Benutzern kommunizieren**.

     ![Screenshot der aktivierten Einstellung "Benutzer können mit anderen Skype for Business- und Teams-Benutzern kommunizieren".](media/manage-external-access-2.png).

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

> [!NOTE]
> Wenn Sie und ein anderer Benutzer sowohl den externen Zugriff aktivieren als auch die Domänen des anderen zulassen, funktioniert das. Wenn es nicht funktioniert, sollte der andere Benutzer sich vergewissern, dass seine Konfiguration Ihre Domäne nicht blockiert.


## <a name="communicate-with-skype-users-in-preview"></a>Kommunizieren mit Skype-Benutzern (in der Vorschau)

Führen Sie die folgenden Schritte aus, damit Teams-Benutzer in Ihrer Organisation mit Skype-Benutzern chatten und diese anrufen können. Teams-Benutzer können dann nach schriftlichen Einzelunterhaltungen oder Audio/Video-Anrufen mit Skype-Benutzern suchen und diese starten.

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**

1. Wechseln Sie im linken Navigationsbereich zu **Organisationsweite Einstellungen** > **Externer Zugriff**.

2. Aktivieren Sie die Einstellung **Benutzer können mit Skype-Benutzern kommunizieren**.

    ![Screenshot der aktivierten Einstellung "Benutzer können mit Skype-Benutzern kommunizieren"](media/manage-external-access-5.png).

Weitere Informationen über die Möglichkeiten der Kommunikation zwischen Teams- und Skype-Benutzern, einschließlich der Einschränkungen, finden Sie unter [Interoperabilität von Teams und Skype](teams-skype-interop.md).

## <a name="common-external-access-scenarios"></a>Häufige Szenarien für den externen Zugriff

|**Ziel**  |**Vorgehensweise**  |
|---------|-----------------------|
|Sie möchten **Microsoft Teams-Benutzern** in Ihrer Organisation die Kommunikation mit **Microsoft Teams-Benutzern** in einer anderen (externen) Organisation ermöglichen.|Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund". Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen.      |
|Sie möchten **Microsoft Teams-Benutzern** in Ihrer Organisation die Kommunikation mit **Skype for Business Online-Benutzern** in derselben Organisation ermöglichen.  |Aktivieren Sie den Koexistenzmodus, oder wählen Sie den Upgrademodus "Inseln" aus, um die Skype for Business-Benutzer in Ihrer Organisation zu unterstützen.   |
|Sie möchten **Microsoft Teams-Benutzern** in Ihrer Organisation die Kommunikation mit **Skype for Business Online-Benutzern** in einer anderen (externen) Organisation ermöglichen.      |Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund". <br><br>Aktivieren Sie die Einstellung **Benutzer können mit anderen Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff". Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen. <br><br>**HINWEIS**: In der externen Domäne mit Skype for Business-Benutzern muss der Koexistenzmodus aktiviert oder der Upgrademodus "Inseln" ausgewählt werden, um die Skype for Business-Benutzer in dieser Organisation zu unterstützen.|
|Lassen Sie **Teams-Benutzer** in Ihrer Organisation mit **Skype for Business lokale Benutzer** in einer anderen (externen) Organisation kommunizieren.      |Fügen Sie unter "Externer Zugriff" die externe Domäne zur Zulassungsliste hinzu, oder verwenden Sie "Öffentlicher Verbund". <br><br>Aktivieren Sie die Einstellung **Benutzer können mit anderen Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff". Lassen Sie den Administrator in der anderen Organisation den lokalen Skype for Business-Server so konfigurieren, dass der Verbund mit Ihrer Domäne zugelassen wird.|
|Ermöglichen Sie **Teams-Benutzern** in Ihrer Organisation die Kommunikation mit **Skype**-Benutzern.<br>  |Aktivieren Sie die Einstellung **Benutzer können mit Skype-Benutzern kommunizieren** unter "Externer Zugriff". |
|Lassen Sie Ihre **Skype for Business Online-Benutzer** mit **Teams-Benutzern** in einem anderen Microsoft 365 oder Office 365 kommunizieren.| Ihre Skype for Business Online-Benutzer können mit Teams-Benutzern in einer anderen Organisation kommunizieren, wenn sich Ihre Benutzer im Upgrademodus "Islands", "SfBOnly", "SfBWIthTeamsCollab" oder "SfBWithTeamsCollabAndMeetings" und die Teams-Benutzer der anderen Organisation im "TeamsOnly"-Modus befinden. <br><br>Aktivieren Sie die Einstellung **Benutzer können mit anderen Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff". Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen.|
|Lassen Sie Ihre **Skype for Business Online-Benutzer** mit **Skype for Business Online-Benutzern** von einem anderen Microsoft 365 oder Office 365 kommunizieren.    | Ihre Skype for Business Online-Benutzer können mit Skype for Business Online-Benutzern in einer anderen Organisation kommunizieren, wenn sich Ihre Benutzer im Upgrademodus "Islands", "SfBOnly", "SfBWIthTeamsCollab" oder "SfBWithTeamsCollabAndMeetings" und die Skype for Business Online-Benutzer der anderen Organisation im Upgrademodus "Islands", "SfBOnly", "SfBWIthTeamsCollab" oder "SfBWithTeamsCollabAndMeetings" befinden.<br><br>Aktivieren Sie die Einstellung **Benutzer können mit anderen Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff". Lassen Sie dann den Administrator in der anderen Microsoft Teams-Organisation dieselben Schritte ausführen.|
|Sie möchten Ihren **Skype for Business Online-Benutzern** die Kommunikation mit **Skype for Business-Benutzern** aus einer lokalen Organisation ermöglichen.     |Ihre Skype for Business Online-Benutzer können mit Skype for Business-Benutzern von einer lokalen Organisation aus kommunizieren, wenn sich die Benutzer in einem der folgenden Aktualisierungsmodi befinden: Islands, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings. <br><br> Aktivieren Sie die Einstellung **Benutzer können mit anderen Skype for Business- und Teams-Benutzern kommunizieren** unter "Externer Zugriff". Lassen Sie den Administrator in der anderen Organisation den lokalen Skype for Business-Server so konfigurieren, dass der Verbund mit Ihrer Domäne zugelassen wird.|
|Sie möchten Ihren **Skype for Business Online-Benutzern** die Kommunikation mit **Skype-Benutzern** (innerhalb oder außerhalb Ihrer Organisation) ermöglichen.   |Aktivieren Sie die Einstellung **Benutzer können mit Skype-Benutzern kommunizieren** unter "Externer Zugriff".|

> [!IMPORTANT]
> Sie müssen keine **Skype-Domänen** als zulässige Domänen hinzufügen, um es Microsoft Teams- oder Skype for Business Online-Benutzern zu ermöglichen, mit Skype-Benutzern innerhalb oder außerhalb Ihrer Organisation zu kommunizieren. Alle **Skype-Domänen** sind in der Whitelist enthalten, das heißt, alle diese Domänen werden als zulässig angesehen.

## <a name="how-does-external-access-compare-with-guest-access"></a>Inwiefern unterscheidet sich der externe Zugriff vom Gastzugriff?

Wenn Sie mehr über den Unterschied zwischen externem Zugriff und Gastzugriff wissen möchten, lesen Sie [Kommunikation mit Benutzern aus anderen Organisationen](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Verwandte Themen

- [Native Chaterfahrung für externe Benutzer (im Verbund)](native-chat-for-external-users.md)
