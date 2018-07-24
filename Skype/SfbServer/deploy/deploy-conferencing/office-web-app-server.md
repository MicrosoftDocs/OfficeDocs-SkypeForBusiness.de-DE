---
title: Konfigurieren der Integration mit Office Web Apps Server in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zum Konfigurieren der Integration von Office Web Apps Server und Skype für Business Server, für PowerPoint-Präsentationen für Webkonferenzen aktivieren.'
ms.openlocfilehash: 558ba648cab4dfd2667251ea96bc83d313746f10
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997314"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Konfigurieren der Integration mit Office Web Apps Server in Skype für Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zum Konfigurieren der Integration von Office Web Apps Server und Skype für Business Server, für PowerPoint-Präsentationen für Webkonferenzen aktivieren.
  
Skype für Business Server setzt Office Web Apps Server zum Verarbeiten von PowerPoint-Präsentationen für Webkonferenzen. Informationen zu den Vorteilen dieses Ansatzes finden Sie unter [Planen von Konferenzen in Skype für Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Bevor Sie Skype für Business Server mit Office Web Apps Server konfigurieren können, müssen Sie sicherstellen, dass die Office Web Apps Server bereits bereitgestellt und konfiguriert ist. Informationen zu Office Web Apps Server, finden Sie im Artikel [Bereitstellen der Infrastruktur: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Nachdem Office Web Apps Server erfolgreich installiert wurde und der Webfarm ordnungsgemäß konfiguriert wird, müssen Sie dann Skype für Business Server durch Hinzufügen von Office Web Apps Server-Such-URL zu Ihrer Skype für Unternehmen die Kommunikation mit dem neuen Server konfigurieren Server-Topologie. 
  
> [!NOTE]
> Die neueste Iteration des Office Web Apps Server heißt Office Online-Server, die von Skype für Business Server unterstützt wird. Weitere Informationen finden Sie in der [Dokumentation zur Office Online-Server](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Konfigurieren von Skype für Business Server zur Kommunikation mit Office Web Apps Server

Gehen Sie dazu wie folgt vor:
  
1.  Skype für Business Server-Topologie-Generator zu öffnen.
    
2. Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus und klicken Sie dann auf **OK**.
    
3. Geben Sie im Dialogfeld **Topologie speichern unter** einen Namen für Ihr Topologiedokument (z. B. **PreWebAppsServerTopology**) im Feld **Dateiname** ein und klicken Sie dann auf **Speichern**. Diese Topologie kann später wieder abgerufen und neu veröffentlicht werden, falls es zu Problemen kommt.
    
4. Erweitern Sie im Topologie-Generator den Eintrag **Skype for Business Server**, erweitern Sie den Namen Ihres Standorts, erweitern Sie **Front-End-Pools der Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Namen eines Ihrer Pools und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
5. Suchen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Überschrift **Office Web Apps-Server zuordnen** und klicken Sie dann auf **Neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus).
    
6. Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
  - Wenn die Office Web Apps Server lokal installiert ist und in derselben Netzwerkzone als Skype für Business Server dann die Option sollte das **Office Web Apps Server in einem externen Netzwerk (d. h., Umkreisnetzwerk/Internet) bereitgestellt wird,** nicht ausgewählt werden.
    
  - Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.
    
7. Klicken Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** auf **OK** und klicken Sie anschließend auf **OK** im Dialogfeld **Eigenschaften bearbeiten**. Die Office Online-Such-URL wird dann unter den Zuordnungen des Pools aufgeführt.
    
Sie müssen diese Schritte für jeden Pool wiederholen, der Ihrem Office Web Apps-Server zugeordnet werden soll.
  
Nachdem Sie die Such-URL zur Topologie hinzugefügt haben, müssen Sie die aktualisierte Topologie veröffentlichen. Gehen Sie dazu im Topologie-Generator wie folgt vor:
  
1. Klicken Sie auf **Aktion** und klicken Sie anschließend auf **Topologie veröffentlichen**.
    
2. Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
3. Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertigstellen**.
    
4. Schließen Sie den Topologie-Generator.
    
## <a name="configure-access-for-external-users"></a>Zugriff für externe Benutzer konfigurieren

Wenn Sie externe Benutzer (d. h., Benutzer, die von außerhalb der Firewall Ihrer Organisation anmelden) möchten haben Zugriff auf Office Web Apps Server PowerPoint-Präsentationen, und Sie müssen Office Web Apps Server und einen Reverseproxyserver verwenden. Sie müssen außerdem eine Website-Veröffentlichungsregel erstellen und konfigurieren, die dazu beiträgt, dass Benutzer eine Verbindung mit dem Server herstellen können. 
  
## <a name="validate-the-configuration"></a>Konfiguration überprüfen

Nachdem Office Web Apps Server zur Topologie hinzugefügt wurde, und die Topologie veröffentlicht wurde, sollten Sie zwei neue Ereignisprotokollereignisse in der Skype für Business Server-Ereignisprotokoll sehen. Zunächst sollte ein LS Daten MCU-Ereignis (Ereignis-ID 41034) hinzugefügt werden. Dieses Ereignis meldet, dass die Office Web Apps Server ermittelt wurde:
  
 **Der Webkonferenzserver Office Web Apps-Server wurde ermittelt, PowerPoint-Inhalte sind aktiviert.**
  
Außerdem sollte ein weiteres "LS Data MCU"-Ereignis angezeigt werden (Ereignis-ID 41032), das Office Web Apps Server-URLs zurückmeldet. Beispielsweise sollten Meldungen wie etwa folgende angezeigt werden:
  
 **Die Ermittlung des Webkonferenzservers Office Web Apps-Server war erfolgreich.**
  
 **Office Web Apps Server-interne referentenseite: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; einbetten =**
  
 **Office Web Apps Server-interne Teilnehmerseite: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; embed = True&amp;=**
  
Wenn Sie den Zugriff für externe Benutzer konfiguriert haben, wird auch etwa angezeigt:
  
 **Office Web Apps Server-externe referentenseite: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; einbetten**
  
 **Office Web Apps Server-interne Teilnehmerseite: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; embed = True&amp;**
  
Wenn Sie, dass ein LS Daten MCU-Ereignis mit der Ereignis-ID des 41033, die die Office Web Apps Server-Ermittlung bedeutet, dass ein Fehler aufgetreten ist sehen. In diesem Fall versucht Skype für Business Server so oft wie gewünscht neu konfiguriert Office Web Apps Server erkennen können. Wenn dieser Prozess, wiederholt fehlschlägt sollten Sie Office Web Apps Server aus Ihrer topologiedokument entfernen, Veröffentlichen der aktualisierten Topologie, und versuchen Sie dann Office Web Apps Server wieder zur Topologie hinzuzufügen, nachdem die Konnektivitätsprobleme behoben wurden.
  
Wenn Office Web Apps Server ordnungsgemäß konfiguriert sein scheint und wurde durch den Suchprozess erkannt können Sie überprüfen, ob Office Web Apps Server funktioniert wie erwartet durch Freigabe einer PowerPoint-Präsentation zwischen einem Paar von Skype für Business-Clients. Wenn Benutzer A kann laden und Anzeigen von die PowerPoint-Präsentation und Benutzer B anschließend an der Besprechung teilnehmen und finden Sie unter diese Präsentation ist Office Web Apps Server funktionsfähig.
  
Auch wenn Office Web Apps Server ordnungsgemäß konfiguriert sein, Sie können potenziell erhalten die Fehlermeldung "einige Freigabefunktionen sind aufgrund von Server-Verbindungsprobleme nicht verfügbar" beim Versuch eine PowerPoint-Präsentation freigeben. Wenn diese Fehlermeldung sollte den Front-End (oder die Server) verknüpft ist, mit dem neuen Office Web Apps Server neu starten.
  

