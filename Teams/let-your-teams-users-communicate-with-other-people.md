---
title: Kommunizieren mit Microsoft Teams-Benutzern in einer anderen Organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Hier erfahren Sie, wie Sie Teams so konfigurieren, dass Benutzer mit Benutzern in einer anderen Organisation kommunizieren können.
ms.openlocfilehash: d974197f6daedab030124dfc1117610e3504ae32
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433191"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Zulassen, dass Ihre Teams-Benutzer in einer anderen Teams-Organisation chatten und mit Benutzern kommunizieren

Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:
  
- Sie verfügen über Benutzer in verschiedenen Domänen in Ihrem Unternehmen. Beispiel: Rob@ContosoEast.com und Ann@ContosoWest.com.
    
- Sie möchten, dass die Personen in Ihrer Organisation Teams verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.
    
- Sie möchten, dass andere Personen in der Welt, die Teams verwenden, Ihre e-Mail-Adresse finden und mit Ihnen Kontakt aufnehmen können. Wenn Sie und ein anderer Benutzer den externen Zugriff aktivieren und die Domänen der anderen Personen zulassen, kann dies funktionieren. Wenn dies nicht funktioniert, sollte der andere Benutzer sicherstellen, dass seine Konfiguration Ihre Domäne nicht blockiert.

Auf diese Weise können Benutzer Sofortnachrichten finden, anrufen und Ihnen senden sowie Besprechungen mit Ihnen einrichten. Wenn Sie möchten, dass externe Benutzer auf Teams und Kanäle zugreifen können, ist der Gastzugriff möglicherweise eine bessere Möglichkeit, um zu gehen. Führen Sie die Schritte in diesem Artikel aus, und stellen Sie sicher, dass Sie den [Gastzugriff aktivieren](set-up-guests.md) , damit die Benutzer kommunizieren können.

> [!IMPORTANT]
> Damit Sie zurzeit innerhalb des Microsoft Teams-Clients an einen externen Benutzer außerhalb Ihrer Organisation, der derzeit kein Gast ihres Aad/Mandanten ist, teilnehmen können, müssen Sie für Hybrid ordnungsgemäß eingerichtet sein und zu Skype for Business Online verschoben werden. Ab 2/25/2019 unterstützt Teams noch keine native Federation, ohne dass der Benutzer das SIP-Profil in Skype for Business Online verwaltet. Weitere Informationen zum Einrichten Ihres Kontos für Hybrid und anschließendes Verschieben in Teams finden Sie unter [Upgrade von Skype for Business-hybridbereitstellung in Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Zulassen, dass Ihre Teams-Benutzer in einer anderen Teams-Organisation chatten und mit Benutzern kommunizieren

Führen Sie die folgenden Schritte aus.

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Schritt 1 – Stellen Sie sicher, dass die erforderlichen Ports und URLs eingerichtet sind.

**Am häufigsten haben Benutzer beim Einrichten der Kommunikation zwischen Unternehmen Probleme damit, die [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) richtig festzulegen.**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Schritt 2 – Aktivieren Ihrer Organisation für die Kommunikation mit einer anderen Teams-Organisation

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt

   1. Navigieren Sie in der linken Navigationsleiste zu **organisationsweiten Einstellungen** > **externer Zugriff**. 

   2. Klicken Sie oben auf der Seite **externer Zugriff** auf **externer** Zugriff auf **ein**. 

   3. Wenn Sie zulassen möchten, dass alle Teams-Organisationen mit Benutzern in Ihrer Organisation kommunizieren, fahren Sie mit Schritt 5 fort. 
   
   4. Wenn Sie einschränken möchten, welche Organisationen mit Benutzern in Ihrer Organisation kommunizieren können, können Sie entweder alle außer einigen Domänen zulassen oder nur bestimmte Organisationen zulassen. Wenn Sie nur einige Domänen zulassen möchten, fügen Sie die zu blockierenden Domänen hinzu, indem Sie auf **Domäne hinzufügen**klicken. Klicken Sie im Bereich **Domäne hinzufügen** im Domänennamen auf **blockiert** und dann auf **Fertig**. Um die Kommunikation auf bestimmte organizatioins zu begrenzen, fügen Sie diese Domänen der Liste mit dem **** Status "verschuldete" hinzu. Nachdem Sie der Zulassungsliste eine beliebige Domäne hinzugefügt haben, sind die Kommunikationen mit anderen Organisationen nur auf die Organisationen limitiert, deren Domänen sich in der Zulassungsliste befinden. 
   
   5. Klicken Sie auf **Speichern**. 

   6. Stellen Sie dann sicher, dass der Administrator in der anderen Teams-Organisation die gleichen Schritte durchführt. In der Liste der **zulässigen Domänen** muss der Administrator beispielsweise die Domäne für Ihr Unternehmen eingeben, wenn er die Unternehmen, die mit seinen Benutzern kommunizieren können, einschränken. 

### <a name="step-3---test-it"></a>Schritt 3 – testen
Um Ihr Setup zu testen, benötigen Sie einen Teams-Benutzer, der sich nicht hinter Ihrer Firewall befindet.
  
   1. Nachdem Sie und der Administrator des Unternehmens die Einstellungen für den **externen Zugriff** geändert haben, sollten Sie gut gehen.
    
   2. Suchen Sie in der Teams-App nach der e-Mail-Adresse der Person, und senden Sie eine Anfrage an den Chat.
    
   3. Bitten Sie Ihren Team-Kontakt, Ihnen eine Anfrage zum Chat zu senden. Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).
    
   4. Eine weitere Möglichkeit, zu testen, ob es sich um eine Firewall handelt, besteht darin, zu einem WLAN-Standort zu wechseln, der sich nicht hinter Ihrer Firewall wie einem Café befindet, und Teams zu verwenden, um eine Anfrage an Ihren Kontakt zu senden, um zu chatten. Wenn die Nachricht dort gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Kommunizieren mit Benutzern in einer Skype for Business Online-Organisation

Wenn Sie Ihre Teams so einrichten, dass Benutzer in einer Skype for Business-Organisation Personen finden und kontaktieren können, die die Kontaktaufnahme mit ihren Benutzern einschränken, bitten Sie den Administrator in dieser Organisation, die folgenden Schritte auszuführen.

![Ein Symbol mit dem Skype for Business-](media/sfb-logo-30x30.png) Logo im **Skype for Business Admin Center** 

Führen Sie den Administrator in dieser Organisation aus, um die folgenden Schritte auszuführen:
    
1. Wechseln Sie im Office 365 Admin Center zu **Admin Center** > **Teams & Skype** > **Legacy-Portal**.
  
2. Wählen Sie im **Skype for Business Admin Center**die Option **Organisation** > **External Communications**aus.
    
3. Um die Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne einzurichten, wählen Sie im Dropdownfeld **nur für zulässige Domänen**aktivieren aus.
    
    Wenn Sie die Kommunikation mit allen anderen Personen in der Welt ermöglichen möchten, die Skype for Business-Richtlinien geöffnet haben, wählen Sie **ein, außer für blockierte Domänen**. Dies ist die Standardeinstellung.
    
4. Wählen **+** Sie unter **blockierte oder zulässige Domänen**den Namen der Domäne aus, die Sie zulassen möchten, und fügen Sie ihn hinzu. Stellen Sie sicher, dass der Administrator in der anderen Organisation dieselben Schritte durchführt. Beispiel: In der Liste der **zugelassenen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.
    
### <a name="related-topics"></a>Verwandte Themen

[Anmelden bei Microsoft Teams](sign-in-teams.md)
-[Endbenutzerschulungen für Teams](enduser-training.md)

