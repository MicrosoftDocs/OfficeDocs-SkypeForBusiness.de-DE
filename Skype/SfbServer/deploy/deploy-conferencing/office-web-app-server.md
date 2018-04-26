---
title: Konfigurieren der Integration mit Office Web Apps Server in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Summary: Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server 2015 to enable PowerPoint presentations for web conferencing.'
ms.openlocfilehash: da6b5765cf62fc97fcc20b72e2411db306b37f0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server-2015"></a>Konfigurieren der Integration mit Office Web Apps Server in Skype for Business Server 2015
 
**Summary:** Read this topic to learn how to configure integration between Office Web Apps Server and Skype for Business Server 2015 to enable PowerPoint presentations for web conferencing.
  
Skype for Business Server employs Office Web Apps Server to handle PowerPoint presentations for web conferencing. For information about the advantages to this approach, see [Plan for conferencing in Skype for Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md).
  
Before you can configure Skype for Business Server to use Office Web Apps Server, you must ensure that Office Web Apps Server is already deployed and configured. For information on Office Web Apps Server, see the article [Deploy the infrastructure: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Skype for Business Server to communicate with the new server by adding the Office Web Apps Server discovery URL to your Skype for Business Server topology. 
  
> [!NOTE]
> The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server 2015. Weitere Details finden Sie in der [Office Online Server-Dokumentationhttps://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Skype for Business Server 2015: Konfigurieren der Integration mit Office Web Apps Server

Gehen Sie dazu wie folgt vor:
  
1.  Open Skype for Business Server Topology Builder.
    
2. Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus und klicken Sie dann auf **OK**.
    
3. Geben Sie im Dialogfeld **Topologie speichern unter** einen Namen für Ihr Topologiedokument (z. B. **PreWebAppsServerTopology**) im Feld **Dateiname** ein und klicken Sie dann auf **Speichern**. Diese Topologie kann später wieder abgerufen und neu veröffentlicht werden, falls es zu Problemen kommt.
    
4. Erweitern Sie im Topologie-Generator den Eintrag **Skype for Business Server**, erweitern Sie den Namen Ihres Standorts, erweitern Sie **Front-End-Pools der Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Namen eines Ihrer Pools und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
5. Suchen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Überschrift **Office Web Apps-Server zuordnen** und klicken Sie dann auf **Neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus).
    
6. Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
  - Wenn der Office Web Apps-Server lokal installiert ist und sich in der gleichen Netzwerkzone wie  befindet, darf die Option Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt nicht aktiviert werden.
    
  - Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.
    
7. Klicken Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** auf **OK** und klicken Sie anschließend auf **OK** im Dialogfeld **Eigenschaften bearbeiten**. Die Office Online-Such-URL wird dann unter den Zuordnungen des Pools aufgeführt.
    
Sie müssen diese Schritte für jeden Pool wiederholen, der Ihrem Office Web Apps-Server zugeordnet werden soll.
  
Nachdem Sie die Such-URL zur Topologie hinzugefügt haben, müssen Sie die aktualisierte Topologie veröffentlichen. Gehen Sie dazu im Topologie-Generator wie folgt vor:
  
1. Klicken Sie auf **Aktion** und klicken Sie anschließend auf **Topologie veröffentlichen**.
    
2. Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
3. Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertigstellen**.
    
4. Schließen Sie den Topologie-Generator.
    
## <a name="configure-access-for-external-users"></a>Zugriff für externe Benutzer konfigurieren

Wenn externe Benutzer (d. h. Benutzer, die sich außerhalb der Firewall Ihrer Organisation anmelden) Zugriff auf PowerPoint-Präsentationen auf  haben sollen, müssen Sie  und einen Reverseproxyserver verwenden. Sie müssen außerdem eine Website-Veröffentlichungsregel erstellen und konfigurieren, die dazu beiträgt, dass Benutzer eine Verbindung mit dem Server herstellen können. 
  
## <a name="validate-the-configuration"></a>Konfiguration überprüfen

After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Skype for Business Server event log. Nachdem  der Topologie hinzugefügt und diese Topologie veröffentlicht wurde, sollten zwei neue Ereignisse im -Ereignisprotokoll angezeigt werden. Als Erstes sollte ein „LS Data MCU“-Ereignis (Ereignis-ID 41034) hinzugefügt worden sein. Dieses Ereignis meldet, dass Office Web Apps-Server erkannt wurde:
  
 **Der Webkonferenzserver Office Web Apps-Server wurde ermittelt, PowerPoint-Inhalte sind aktiviert.**
  
Außerdem sollte ein weiteres "LS Data MCU"-Ereignis angezeigt werden (Ereignis-ID 41032), das Office Web Apps Server-URLs zurückmeldet. Beispielsweise sollten Meldungen wie etwa folgende angezeigt werden:
  
 **Die Ermittlung des Webkonferenzservers Office Web Apps-Server war erfolgreich.**
  
 Die interne Referentenseite von Office Web Apps-Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&embed=
  
 Die interne Teilnehmerseite von Office Web Apps-Server: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&embed=true&=
  
Wenn Sie den Zugriff für externe Benutzer konfiguriert haben, sehen Sie auch etwa Folgendes:
  
 Die externe Referentenseite von Office Web Apps-Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&embed
  
 Die interne Teilnehmerseite von Office Web Apps-Server: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&embed=true&=
  
Wenn Sie ein „LS Data MCU“-Ereignis mit der Ereignis-ID 41033 sehen, bedeutet das, dass bei der-Ermittlung ein Fehler aufgetreten ist. In that case, Skype for Business Server will try as many times as needed to discover the newly-configured Office Web Apps Server. Führt der Ermittlungsprozess mehrmals nicht zum Erfolg, sollten Sie Office Web Apps-Server aus dem Topologiedokument entfernen, die aktualisierte Topologie veröffentlichen und dann nach dem Beheben der Verbindungsprobleme versuchen,  wieder zu der Topologie hinzuzufügen.
  
Wenn  offensichtlich korrekt konfiguriert und vom Ermittlungsprozess erkannt worden ist, können Sie sicherstellen, dass  wie erwartet funktioniert, indem Sie eine PowerPoint-Präsentation zwischen einem -Clientpaar freigeben. Wenn Benutzer A die PowerPoint-Präsentation laden und anzeigen und Benutzer B dann der Besprechung beitreten und die Präsentation sehen kann, funktioniert  einwandfrei.
  
Auch wenn  anscheinend korrekt konfiguriert ist, kann es sein, dass Sie die folgende Fehlermeldung erhalten, wenn Sie versuchen, eine PowerPoint-Präsentation freizugeben: „Einige Freigabefunktionen sind aufgrund von Serververbindungsproblemen nicht verfügbar“. Wenn Sie diese Fehlermeldung erhalten, sollten Sie die Front-End-Server, die dem neuen  zugeordnet sind, neu starten.
  

