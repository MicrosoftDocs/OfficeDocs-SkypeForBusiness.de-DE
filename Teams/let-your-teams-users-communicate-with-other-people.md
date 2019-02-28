---
title: Kommunizieren mit Microsoft Teams-Benutzern in einer anderen Organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Finden Sie unter Konfigurieren von Teams, damit die Benutzer mit Benutzern in anderen Organisationen kommunizieren können.
ms.openlocfilehash: 664c459f85d3a6657c0e556d19d92b7b278f0aee
ms.sourcegitcommit: ea1085228894ae448f575f9e13a9f25a1f47e636
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2019
ms.locfileid: "30312276"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Lassen Sie Ihren Teams Benutzer Chat und kommunizieren mit Benutzern in einer anderen Organisation von Teams

Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:
  
- Sie müssen die Benutzer in unterschiedlichen Domänen in Ihrem Unternehmen. Beispiel: Rob@ContosoEast.com und Ann@ContosoWest.com.
    
- Sie möchten die Personen in Ihrer Organisation Teams verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.
    
- Sie möchten Personen in der ganzen Welt, die Teams verwendet wird, in der Lage, zu finden, und wenden Sie sich mithilfe Ihrer e-Mail-Adresse sein. Wenn Sie und ein weiterer Benutzer aktivieren des externen Zugriffs und des jeweils anderen Domänen ermöglichen, diese verwendet werden. Wenn sie nicht funktioniert, der andere Benutzer sollten sicherstellen, dass seine oder ihre Konfiguration Ihrer Domäne blockieren nicht zur Verfügung.

Dadurch können Benutzer zu suchen, aufrufen, und Ihnen Sofortnachrichten senden, sowie Besprechungen mit Ihnen einrichten. Wenn Sie externe Benutzer auf Teams und Kanäle zugreifen möchten, möglicherweise Gast Access eine bessere Möglichkeit zum wechseln. Führen Sie die Schritte in diesem Artikel und stellen Sie sicher, dass zum [Aktivieren des Zugriffs Gast](set-up-guests.md) Benutzer kommunizieren können.

> [!IMPORTANT]
> Um die derzeit in der Microsoft-Teams-Client an einen externen Benutzer außerhalb Ihrer Organisation einen Verbund einrichten, die zurzeit nicht Gastsystem Ihres AAD-Mandanten wird, muss korrekt Setup für hybride und in Skype für Business Online verschoben. Ab 2/25/2019 Teams noch unterstützt keine systemeigene Verbund, ohne dass der Benutzer des SIP-Profils wird in Skype für Business Online verwaltet. Weitere Informationen zur Einstellung Ihr Konto für Hybrid und klicken Sie dann auf Teams verschoben, finden Sie unter [Upgrade Skype für Business Hybridbereitstellung Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Lassen Sie Ihren Teams Benutzer Chat und kommunizieren mit Benutzern in einer anderen Organisation von Teams

Gehen Sie folgendermaßen vor.

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>Schritt 1: Stellen Sie sicher, dass Sie richten Sie die Ports und URLs, die erforderlich sind.

**Am häufigsten haben Benutzer beim Einrichten der Kommunikation zwischen Unternehmen Probleme damit, die [URLs und IP-Adressbereiche von Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) richtig festzulegen.**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>Schritt 2: Aktivieren Ihrer Organisation, um die Kommunikation mit einer anderen Organisation von Teams

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**

   1. Wechseln Sie im linken Navigationsbereich **Org geltende**Einstellungen > **externen Zugriff**. 

   2. Klicken Sie am oberen Rand der Seite **externen Zugriff** auf **externen Zugriff** auf **aktiviert**. 

   3. Wenn Sie alle Teams Organisationen die Kommunikation mit Benutzern in Ihrer Organisation zulassen möchten, überspringen Sie Schritt 5. 
   
   4. Wenn Sie möchten beschränken, welche Organisationen kommunizieren können mit Benutzern in Ihrer Organisation können Sie alle jedoch einige Domänen zulassen oder nur bestimmte Organisationen zulassen. Um alle jedoch einige Domänen zu ermöglichen, fügen Sie die Domänen an, den, die Sie blockieren, indem Sie auf **Domäne hinzufügen**möchten. Klicken Sie im Bereich **Domäne hinzufügen** tragen Sie den Domänennamen ein Klicken Sie auf **blockiert** und klicken Sie dann auf **Fertig**. Um für die Kommunikation mit bestimmten Organizatioins zu beschränken, fügen Sie diese Domänen zu der Liste mit dem Status **Alowed**. Nachdem Sie eine beliebige Domäne der Zulassungsliste hinzugefügt haben, werden für die Kommunikation mit anderen Organisationen auf nur Organisationen beschränkt, deren Domänen in der Zulassungsliste enthalten sind. 
   
   5. Klicken Sie auf **Speichern**. 

   6. Stellen Sie sicher, dass der Administrator in der anderen Teams Organisation dieselben Schritte wird. Beispielsweise muss in ihrer Liste der **zulässigen Domänen** ihren Administrator um die Domäne für Ihr Unternehmen einzugeben, falls sie einschränken, die Organisationen mit ihren Benutzern kommunizieren können. 

### <a name="step-3---test-it"></a>Schritt 3: Testen sie das Formular
Um die Installation zu testen, benötigen Sie ein Teams-Benutzer, die nicht hinter der Firewall befindet.
  
   1. Nachdem Sie und der Administrator aus der Organisation die **Zugriff durch externe** Einstellungen geändert haben, sollten Sie gut zu wechseln.
    
   2. In der app Teams nach e-Mail-Adresse der Person suchen Sie, und senden Sie eine Anforderung zum chat.
    
   3. Bitten Sie Ihren Teams Kontakt senden eine Anforderung an chat. Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).
    
   4. Eine andere Möglichkeit zu prüfen, ob das Problem der Firewall ist ist, gehen Sie an einem Speicherort Wifi nicht hinter der Firewall wie einem Café und Teams das Senden einer Anforderung an den Kontakt zu chat verwenden. Wenn die Nachricht dort gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Kommunizieren Sie mit Benutzern in einer Skype für Business Online-Organisation

Wenn Sie es einrichten können Ihre Teams Benutzer suchen und Kontakt Benutzer, die in einer Skype für Business-Organisation beschränkt sind, die die Benutzer eine Verbindung herstellen kann, fragt den Administrator in der Organisation an die folgenden Schritte ausführen.

![SFB-Logo-30x30.png](media/sfb-logo-30x30.png) **Mithilfe von Skype für Business Administrationscenter** 

Haben Sie die Admin, Organisation führen Sie diese Schritte:
    
1. Wechseln Sie in das Office 365 Administrationscenter zu **Admin Center** > **Teams & Skype** > **Legacy-Portal**.
  
2. Wählen Sie unter **Skype for Business Admin Center**die Option **Organisation** > **Externe Kommunikation**.
    
3. Zum Einrichten der Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne, in der Dropdown-Feld auswählen **auf nur für zulässige Domänen**.
    
    ODER, falls sie Kommunikation mit allen anderen Benutzern in der ganzen Welt aktivieren, hat öffnen, möchten Skype für Geschäftsrichtlinien, wählen **auf mit Ausnahme der blockierten Domänen**. Dies ist die Standardeinstellung.
    
4. Wählen Sie unter **blockiert oder zugelassenen Domänen**, **+** , und fügen Sie den Namen der Domäne, die Sie zulassen möchten. Stellen Sie sicher, dass der Administrator in der anderen Organisation dieselben Schritte wird. Beispiel: In der Liste der **zugelassenen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.
    
### <a name="related-topics"></a>Verwandte Themen

[Melden Sie sich bei Microsoft-Teams,](sign-in-teams.md)
[Endbenutzer Schulungen für Teams](enduser-training.md)

