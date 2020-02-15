---
title: Konfigurieren der Integration mit Office-webapps Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Zusammenfassung: in diesem Thema erfahren Sie, wie Sie die Integration von Office Web Apps Server und Skype for Business Server konfigurieren, um PowerPoint-Präsentationen für Webkonferenzen zu aktivieren.'
ms.openlocfilehash: fee5939e8441457e3cee66e266baacd144ada288
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983920"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Konfigurieren der Integration mit Office-webapps Server in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um zu erfahren, wie Sie die Integration zwischen Office Web Apps Server und Skype for Business Server konfigurieren, um PowerPoint-Präsentationen für Webkonferenzen zu aktivieren.
  
Skype for Business Server verwendet Office-webapps-Server, um PowerPoint-Präsentationen für Webkonferenzen zu behandeln. Informationen zu den Vorteilen dieses Ansatzes finden Sie unter [Plan for Conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md).
  
Bevor Sie Skype for Business Server für die Verwendung von Office-webapps Server konfigurieren können, müssen Sie sicherstellen, dass Office-webapps-Server bereits bereitgestellt und konfiguriert ist. Informationen zu Office-webapps Server finden Sie im Artikel [Bereitstellen der Infrastruktur: Office Online Server](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Nachdem Sie Office-webapps Server erfolgreich installiert und die Webfarm ordnungsgemäß konfiguriert haben, müssen Sie Skype for Business Server für die Kommunikation mit dem neuen Server konfigurieren, indem Sie die Office-webapps Server-Erkennungs-URL zu Ihrem Skype for Business hinzufügen. Server Topologie. 
  
> [!NOTE]
> Die neueste Iteration von Office-webapps Server wird Office Online Server benannt, der von Skype for Business Server unterstützt wird. Weitere Informationen finden Sie in der [Dokumentation zum Office Online Server](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx). 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Konfigurieren Skype for Business Server für die Kommunikation mit Office-webapps Server

Gehen Sie dazu wie folgt vor:
  
1. Öffnen Sie Skype for Business Server Topologie-Generator.
    
2. Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus einer vorhandenen Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.
    
3. Geben Sie im Dialogfeld **Topologie speichern unter** einen Namen für Ihr Topologiedokument (z. B. **PreWebAppsServerTopology**) in **Dateiname** ein, und klicken Sie dann auf **Speichern**. Diese Topologie kann später wieder abgerufen und neu veröffentlicht werden, falls es zu Problemen kommt.
    
4. Erweitern Sie im Topologie-Generator **Skype for Business Server**, erweitern Sie den Namen Ihres Standorts, erweitern Sie **Enterprise Edition-Front-End-Pools**, klicken Sie mit der rechten Maustaste auf den Namen eines Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
5. Suchen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Überschrift **Office Web Apps-Server zuordnen**, und klicken Sie dann auf **Neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus).
    
6. Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
   - Wenn der Office Web Apps-Server lokal und in der gleichen Netzwerkzone wie Skype for Business Server installiert ist, sollte die Option **Office Web Apps Server in einem externen Netzwerk bereitgestellt werden (d. "Perimeter/Internet")** sollte nicht ausgewählt werden.
    
   - Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.
    
7. Klicken Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** auf **OK**, und klicken Sie dann auf **OK** im Dialogfeld **Eigenschaften bearbeiten**. Die Discovery-URL wird dann als eine der Zuordnungen des Pools aufgeführt.
    
Sie müssen diese Schritte für jeden Pool wiederholen, der Ihrem Office Web Apps-Server zugeordnet werden soll.
  
Nachdem Sie die Discovery-URL zur Topologie hinzugefügt haben, müssen Sie die aktualisierte Topologie veröffentlichen. Gehen Sie dazu im Topologie-Generator wie folgt vor:
  
1. Klicken Sie auf **Aktion**, und klicken Sie dann auf **Topologie veröffentlichen**.
    
2. Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
3. Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.
    
4. Schließen Sie den Topologie-Generator.
    
## <a name="configure-access-for-external-users"></a>Konfigurieren des Zugriffs für externe Benutzer

Wenn Sie möchten, dass externe Benutzer (also Benutzer, die sich außerhalb der Firewall Ihrer Organisation anmelden) Zugriff auf Office-webapps Server-PowerPoint-Präsentationen haben sollen, müssen Sie Office-webappsserver und einen Reverse-Proxy Server verwenden. Außerdem müssen Sie eine Website Veröffentlichungsregel erstellen und konfigurieren, mit der sichergestellt wird, dass Benutzer eine Verbindung mit dem Server herstellen können. 
  
## <a name="validate-the-configuration"></a>Überprüfen der Konfiguration

Nachdem Office webapps Server zur Topologie hinzugefügt wurde und diese Topologie veröffentlicht wurde, sollten im Skype for Business Server Ereignisprotokoll zwei neue Ereignisprotokoll Ereignisse angezeigt werden. Zunächst sollte ein ls Data MCU-Ereignis (Ereigniskennung 41034) hinzugefügt werden; Dieses Ereignis meldet, dass der Office-webapps-Server erkannt wurde:
  
 **Webkonferenzserver Office-webapps-Server wird ermittelt, PowerPoint-Inhalte sind aktiviert.**
  
Darüber hinaus sollte ein weiteres ls Data MCU-Ereignis (Ereigniskennung 41032) angezeigt werden, das Office-webapps-Server-URLs zurückgibt. Beispielsweise sollten Sie etwas Ähnliches sehen:
  
 **Die Office-webapps-Server Ermittlung für den Webkonferenzserver ist erfolgreich.**
  
 **Interne Office-webapps-Server- https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&ampReferenten Seite:; embed =**
  
 **Interne Office webapps Server-Teilnehmerseite: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp; embed = true&amp;=**
  
Wenn Sie den Zugriff für externe Benutzer konfiguriert haben, sehen Sie auch eine ähnliche Vorgehensweise:
  
 **Externe Referenten Seite von Office-webapps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp; einbetten**
  
 **Interne Office webapps Server-Teilnehmerseite: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp>;**
  
Wenn ein ls Data MCU-Ereignis mit der Ereignis-ID 41033 angezeigt wird, bedeutet dies, dass die Ermittlung von Office-webapps-Servern fehlgeschlagen ist. In diesem Fall versucht Skype for Business Server so oft wie erforderlich, den neu konfigurierten Office-webapps-Server zu ermitteln. Wenn der Ermittlungsprozess wiederholt fehlschlägt, sollten Sie Office-webappsserver aus Ihrem Topologie-Dokument entfernen, die aktualisierte Topologie veröffentlichen und dann Office-webapps-Server wieder der Topologie hinzufügen, nachdem die Verbindungsprobleme behoben wurden.
  
Wenn Office-webapps-Server anscheinend ordnungsgemäß konfiguriert ist und durch den Ermittlungsprozess erkannt wurde, können Sie sicherstellen, dass Office-webapps Server wie erwartet funktioniert, indem Sie eine PowerPoint-Präsentation zwischen einem Paar Skype for Business Clients freigeben. Wenn Benutzer a die PowerPoint-Präsentation laden und anzeigen kann und wenn Benutzer B dann an der Besprechung teilnehmen und diese Präsentation sehen kann, funktioniert Office-webapps-Server.
  
Selbst wenn Office-webapps-Server anscheinend ordnungsgemäß konfiguriert ist, könnten Sie möglicherweise die Fehlermeldung "einige Freigabefunktionen sind aufgrund von Server Verbindungsproblemen nicht verfügbar" erhalten, wenn Sie versuchen, eine PowerPoint-Präsentation freizugeben. Wenn Sie diese Fehlermeldung erhalten, sollten Sie den Front-End-Server (oder Server) neu starten, der dem neuen Office-webapps-Server zugeordnet ist.
  

