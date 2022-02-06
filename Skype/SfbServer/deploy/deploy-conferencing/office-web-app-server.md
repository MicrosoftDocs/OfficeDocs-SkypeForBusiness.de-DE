---
title: Konfigurieren der Integration mit Office Web Apps-Server in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie die Integration zwischen Office Web Apps Server und Skype for Business Server konfigurieren, um PowerPoint Präsentationen für Webkonferenzen zu aktivieren.'
---

# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Konfigurieren der Integration mit Office Web Apps-Server in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Integration zwischen Office Web Apps Server und Skype for Business Server konfigurieren, um PowerPoint Präsentationen für Webkonferenzen zu aktivieren.
  
Skype for Business Server verwendet Office Web Apps-Server, um PowerPoint Präsentationen für Webkonferenzen zu verarbeiten. Informationen zu den Vorteilen dieses Ansatzes finden Sie unter [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Bevor Sie Skype for Business Server für die Verwendung Office Web Apps-Servers konfigurieren können, müssen Sie sicherstellen, dass Office Web Apps-Server bereits bereitgestellt und konfiguriert ist. Informationen zu Office Web Apps Server finden Sie im Artikel ["Bereitstellen der Infrastruktur: Office Online Server](/webappsserver/deploy-the-infrastructure-office-web-apps-server)". 
  
Nachdem Office Web Apps-Server erfolgreich installiert und Die Webfarm ordnungsgemäß konfiguriert wurde, müssen Sie Skype for Business Server für die Kommunikation mit dem neuen Server konfigurieren, indem Sie der Office Web Apps Server Discovery-URL zu Ihrer Skype for Business Server Topologie hinzufügen. 
  
> [!NOTE]
> Die neueste Iteration von Office Web Apps-Server heißt Office Online Server, die von Skype for Business Server unterstützt wird. Weitere Informationen finden Sie in der [Office Online Server Dokumentation](/officeonlineserver/office-online-server). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Konfigurieren Skype for Business Server für die Kommunikation mit Office Web Apps Server

Gehen Sie dazu wie folgt vor:
  
1. Öffnen Sie Skype for Business Server Topologie-Generator.
    
2. Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus einer vorhandenen Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.
    
3. Geben Sie im Dialogfeld **Topologie speichern unter** einen Namen für Ihr Topologiedokument (z. B. **PreWebAppsServerTopology**) in **Dateiname** ein, und klicken Sie dann auf **Speichern**. Diese Topologie kann später wieder abgerufen und neu veröffentlicht werden, falls es zu Problemen kommt.
    
4. Erweitern Sie im Topologie-Generator **Skype for Business Server**, erweitern Sie den Namen Ihres Standorts, erweitern Sie **Enterprise Edition Front-End-Pools**, klicken Sie mit der rechten Maustaste auf den Namen eines Pools, und klicken Sie dann auf **"Eigenschaften bearbeiten**".
    
5. Suchen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Überschrift **Office Web Apps-Server zuordnen**, und klicken Sie dann auf **Neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus).
    
6. Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
   - Wenn der Office Web Apps-Server lokal installiert ist und sich in derselben Netzwerkzone wie Skype for Business Server sollte die Option **Office Web Apps-Server in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt wird,** nicht ausgewählt werden.
    
   - Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.
    
7. Klicken Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** auf **OK**, und klicken Sie dann auf **OK** im Dialogfeld **Eigenschaften bearbeiten**. Die Ermittlungs-URL wird dann als eine der Zuordnungen des Pools aufgelistet.
    
Sie müssen diese Schritte für jeden Pool wiederholen, der Ihrem Office Web Apps-Server zugeordnet werden soll.
  
Nachdem Sie die Ermittlungs-URL zur Topologie hinzugefügt haben, müssen Sie die aktualisierte Topologie veröffentlichen. Gehen Sie dazu im Topologie-Generator wie folgt vor:
  
1. Klicken Sie auf **Aktion**, und klicken Sie dann auf **Topologie veröffentlichen**.
    
2. Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
3. Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.
    
4. Schließen Sie den Topologie-Generator.
    
## <a name="configure-access-for-external-users"></a>Konfigurieren des Zugriffs für externe Benutzer

Wenn externe Benutzer (d. h. Benutzer, die sich von außerhalb der Firewall Ihrer Organisation anmelden) Zugriff auf Office Web Apps Server PowerPoint Präsentationen haben sollen, müssen Sie Office Web Apps-Server und einen Reverseproxyserver verwenden. Außerdem müssen Sie eine Websiteveröffentlichungsregel erstellen und konfigurieren, mit der sichergestellt wird, dass Benutzer eine Verbindung mit dem Server herstellen können. 
  
## <a name="validate-the-configuration"></a>Überprüfen der Konfiguration

Nachdem Office Web Apps-Server der Topologie hinzugefügt wurde, und nachdem diese Topologie veröffentlicht wurde, sollten im Skype for Business Server Ereignisprotokoll zwei neue Ereignisprotokollereignisse angezeigt werden. Zunächst sollte ein LS Data MCU-Ereignis (Ereignis-ID 41034) hinzugefügt werden. Dieses Ereignis meldet, dass der Office Web Apps-Server ermittelt wurde:
  
 **Webkonferenzserver Office Web Apps-Server ermittelt wird, PowerPoint Inhalt aktiviert ist.**
  
Außerdem sollte ein weiteres LS Data MCU-Ereignis (Ereignis-ID 41032) angezeigt werden, das Office Web Apps Server-URLs zurückgibt. Sie sollten z. B. etwas ähnliches sehen:
  
 **Die Webkonferenzserver-Office Web Apps-Serverermittlung ist erfolgreich.**
  
 **Office interne Referentenseite des Web Apps-Servers: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed=**
  
 **Office Interne Teilnehmerseite des Web Apps-Servers: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp;=**
  
Wenn Sie den Zugriff für externe Benutzer konfiguriert haben, sehen Sie auch etwas ähnliches wie:
  
 **externe Referentenseite für Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp;embed**
  
 **Office Interne Teilnehmerseite des Web Apps-Servers: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**
  
Wenn ein LS Data MCU-Ereignis mit der Ereignis-ID 41033 angezeigt wird, bedeutet dies, dass Office Web Apps-Serverermittlung fehlgeschlagen ist. In diesem Fall versuchen Skype for Business Server so oft wie nötig, den neu konfigurierten Office Web Apps-Server zu ermitteln. Wenn der Ermittlungsprozess wiederholt fehlschlägt, sollten Sie Office Web Apps-Server aus ihrem Topologiedokument entfernen, die aktualisierte Topologie veröffentlichen und dann versuchen, Office Web Apps Server wieder zur Topologie hinzuzufügen, nachdem die Verbindungsprobleme behoben wurden.
  
Wenn Office Web Apps-Server ordnungsgemäß konfiguriert zu sein scheint und vom Ermittlungsprozess erkannt wurde, können Sie überprüfen, ob Office Web Apps-Server erwartungsgemäß funktioniert, indem Sie eine PowerPoint Präsentation zwischen einem Paar Skype for Business Clients freigeben. Wenn Benutzer A die PowerPoint Präsentation laden und anzeigen kann und Benutzer B dann an der Besprechung teilnehmen und diese Präsentation anzeigen kann, funktioniert Office Web Apps-Server.
  
Auch wenn Office Web Apps-Server ordnungsgemäß konfiguriert zu sein scheint, erhalten Sie möglicherweise die Fehlermeldung "Einige Freigabefeatures sind aufgrund von Serverkonnektivitätsproblemen nicht verfügbar", wenn Sie versuchen, eine PowerPoint Präsentation freizugeben. Wenn diese Fehlermeldung angezeigt wird, sollten Sie den Front-End-Server (oder die Server) neu starten, der dem neuen Office Web Apps-Server zugeordnet ist.
