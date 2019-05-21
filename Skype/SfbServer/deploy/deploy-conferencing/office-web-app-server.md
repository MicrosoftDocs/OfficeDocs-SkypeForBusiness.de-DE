---
title: Konfigurieren der Integration in Office Web Apps Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die Integration zwischen Office Web Apps Server und Skype for Business Server so konfigurieren, dass PowerPoint-Präsentationen für Webkonferenzen aktiviert werden.'
ms.openlocfilehash: e657820a7a44197a344f23a67fdcd42ce0e593a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289111"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Konfigurieren der Integration in Office Web Apps Server in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Integration zwischen Office Web Apps Server und Skype for Business Server so konfigurieren, dass PowerPoint-Präsentationen für Webkonferenzen aktiviert werden.
  
Skype for Business Server verwendet Office Web Apps Server für die Behandlung von PowerPoint-Präsentationen für Webkonferenzen. Informationen zu den Vorteilen dieses Ansatzes finden Sie unter [Planen von Konferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Bevor Sie Skype for Business Server für die Verwendung von Office Web Apps Server konfigurieren können, müssen Sie sicherstellen, dass Office Web Apps Server bereits bereitgestellt und konfiguriert ist. Informationen zu Office Web Apps Server finden Sie im Artikel [Bereitstellen der Infrastruktur: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Nachdem Office Web Apps Server erfolgreich installiert und ihre Webfarm ordnungsgemäß konfiguriert wurde, müssen Sie Skype for Business Server für die Kommunikation mit dem neuen Server konfigurieren, indem Sie die URL der Office Web Apps Server Discovery zu Ihrem Skype for Business hinzufügen. Server Topologie. 
  
> [!NOTE]
> Die neueste Iteration von Office Web Apps Server heißt Office Online Server, das von Skype for Business Server unterstützt wird. Weitere Informationen finden Sie in der [Office Online Server-Dokumentation](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Konfigurieren von Skype for Business Server für die Kommunikation mit Office Web Apps Server

Gehen Sie dazu wie folgt vor:
  
1. Öffnen Sie den Skype for Business Server-Topologie-Generator.
    
2. Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus und klicken Sie dann auf **OK**.
    
3. Geben Sie im Dialogfeld **Topologie speichern unter** einen Namen für Ihr Topologiedokument (z. B. **PreWebAppsServerTopology**) im Feld **Dateiname** ein und klicken Sie dann auf **Speichern**. Diese Topologie kann später wieder abgerufen und neu veröffentlicht werden, falls es zu Problemen kommt.
    
4. Erweitern Sie im Topologie-Generator den Eintrag **Skype for Business Server**, erweitern Sie den Namen Ihres Standorts, erweitern Sie **Front-End-Pools der Enterprise Edition**, klicken Sie mit der rechten Maustaste auf den Namen eines Ihrer Pools und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
5. Suchen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Überschrift **Office Web Apps-Server zuordnen** und klicken Sie dann auf **Neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus).
    
6. Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
   - Wenn der Office Web Apps-Server lokal und in derselben Netzwerkzone wie Skype for Business Server installiert ist, sollte die Option **Office Web Apps Server in einem externen Netzwerk bereitgestellt werden (also Umkreis/Internet)** , nicht ausgewählt werden.
    
   - Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.
    
7. Klicken Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** auf **OK** und klicken Sie anschließend auf **OK** im Dialogfeld **Eigenschaften bearbeiten**. Die Office Online-Such-URL wird dann unter den Zuordnungen des Pools aufgeführt.
    
Sie müssen diese Schritte für jeden Pool wiederholen, der Ihrem Office Web Apps-Server zugeordnet werden soll.
  
Nachdem Sie die Such-URL zur Topologie hinzugefügt haben, müssen Sie die aktualisierte Topologie veröffentlichen. Gehen Sie dazu im Topologie-Generator wie folgt vor:
  
1. Klicken Sie auf **Aktion** und klicken Sie anschließend auf **Topologie veröffentlichen**.
    
2. Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
3. Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertigstellen**.
    
4. Schließen Sie den Topologie-Generator.
    
## <a name="configure-access-for-external-users"></a>Zugriff für externe Benutzer konfigurieren

Wenn Sie externe Benutzer (also Benutzer, die sich außerhalb der Firewall Ihrer Organisation anmelden) für den Zugriff auf Office Web Apps Server PowerPoint-Präsentationen verwenden möchten, müssen Sie Office Web Apps Server und einen Reverse Proxy Server verwenden. Sie müssen außerdem eine Website-Veröffentlichungsregel erstellen und konfigurieren, die dazu beiträgt, dass Benutzer eine Verbindung mit dem Server herstellen können. 
  
## <a name="validate-the-configuration"></a>Konfiguration überprüfen

Nachdem Office Web Apps Server zur Topologie hinzugefügt wurde und die Topologie veröffentlicht wurde, sollten im Skype for Business Server-Ereignisprotokoll zwei neue Ereignisprotokoll Ereignisse angezeigt werden. Zunächst sollte ein ls-Daten MCU-Ereignis (Ereignis-ID 41034) hinzugefügt werden. Dieses Ereignis meldet, dass der Office Web Apps-Server erkannt wurde:
  
 **Der Webkonferenzserver Office Web Apps-Server wurde ermittelt, PowerPoint-Inhalte sind aktiviert.**
  
Außerdem sollte ein weiteres "LS Data MCU"-Ereignis angezeigt werden (Ereignis-ID 41032), das Office Web Apps Server-URLs zurückmeldet. Beispielsweise sollten Meldungen wie etwa folgende angezeigt werden:
  
 **Die Ermittlung des Webkonferenzservers Office Web Apps-Server war erfolgreich.**
  
 **Office Web Apps Server-interne Referenten https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampSeite:; Einbetten =**
  
 **Office Web Apps Server-interne Teilnehmer- https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&ampSeite:; Einbetten = wahr&amp;=**
  
Wenn Sie den Zugriff für externe Benutzer konfiguriert haben, sehen Sie auch etwas ähnliches wie:
  
 **Office Web Apps Server-externe Referenten https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampSeite:; Einbetten**
  
 **Office Web Apps Server-interne Teilnehmer- <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>Seite:;**
  
Wenn ein ls-Daten MCU-Ereignis mit der Ereignis-ID von 41033 angezeigt wird, bedeutet dies, dass die Server Ermittlung von Office Web Apps fehlgeschlagen ist. In diesem Fall wird Skype for Business Server so oft wie erforderlich versuchen, um den neu konfigurierten Office Web Apps-Server zu entdecken. Wenn der Ermittlungsvorgang wiederholt fehlschlägt, sollten Sie Office Web Apps Server aus Ihrem Topologie-Dokument entfernen, die aktualisierte Topologie veröffentlichen und dann versuchen, Office Web Apps Server wieder zur Topologie hinzuzufügen, nachdem die Verbindungsprobleme behoben wurden.
  
Wenn Office Web Apps Server anscheinend ordnungsgemäß konfiguriert wurde und vom Ermittlungsprozess erkannt wurde, können Sie überprüfen, ob der Office Web Apps-Server wie erwartet funktioniert, indem Sie eine PowerPoint-Präsentation zwischen einem Paar von Skype for Business-Clients freigeben. Wenn Benutzer a die PowerPoint-Präsentation laden und anzeigen kann und wenn Benutzer B dann an der Besprechung teilnehmen und diese Präsentation sehen kann, funktioniert der Office Web Apps-Server.
  
Auch wenn Office Web Apps Server anscheinend richtig konfiguriert ist, können Sie möglicherweise die Fehlermeldung "einige Freigabefeatures sind aufgrund von Server Verbindungsproblemen nicht verfügbar" erhalten, wenn Sie versuchen, eine PowerPoint-Präsentation freizugeben. Wenn diese Fehlermeldung angezeigt wird, sollten Sie den Front-End-Server (oder die Server) neu starten, die dem neuen Office Web Apps-Server zugeordnet sind.
  

