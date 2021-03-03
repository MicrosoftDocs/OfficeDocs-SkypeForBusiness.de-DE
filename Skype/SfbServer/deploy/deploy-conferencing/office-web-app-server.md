---
title: Konfigurieren der Integration mit Office Web Apps Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7e9149e-bf16-4120-afe0-3ee09c88f5eb
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie die Integration zwischen Office Web Apps Server und Skype for Business Server konfigurieren, um PowerPoint-Präsentationen für Webkonferenzen zu aktivieren.'
ms.openlocfilehash: 005bd9fe7d7fece7d488935002e7146fc5a9ffe4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820465"
---
# <a name="configure-integration-with-office-web-apps-server-in-skype-for-business-server"></a>Konfigurieren der Integration mit Office Web Apps Server in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Integration zwischen Office Web Apps Server und Skype for Business Server konfigurieren, um PowerPoint Präsentationen für Webkonferenzen zu aktivieren.
  
Skype for Business Server verwendet Office Web Apps Server für die Verarbeitung von PowerPoint-Präsentationen für Webkonferenzen. Informationen zu den Vorteilen dieses Ansatzes finden Sie unter "Planen von [Konferenzen in Skype for Business Server".](../../plan-your-deployment/conferencing/conferencing.md)
  
Bevor Sie Skype for Business Server für die Verwendung von Office Web Apps Server konfigurieren können, müssen Sie sicherstellen, dass Office Web Apps Server bereits bereitgestellt und konfiguriert ist. Informationen zu Office Web Apps Server finden Sie im Artikel ["Bereitstellen der Infrastruktur: Office Online Server "](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Nachdem Office Web Apps Server erfolgreich installiert und Ihre Webfarm ordnungsgemäß konfiguriert wurde, müssen Sie Skype for Business Server für die Kommunikation mit dem neuen Server konfigurieren, indem Sie ihrer Skype for Business Server-Topologie die Office Web Apps Server-Such-URL hinzufügen. 
  
> [!NOTE]
> Die neueste Iteration von Office Web Apps Server heißt Office Online Server, das von Skype for Business Server unterstützt wird. Weitere Informationen finden Sie in der [Office Online Server-Dokumentation.](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx) 
  
## <a name="configure-skype-for-business-server-to-communicate-with-office-web-apps-server"></a>Konfigurieren von Skype for Business Server für die Kommunikation mit Office Web Apps Server

Gehen Sie dazu wie folgt vor:
  
1. Öffnen Sie den Skype for Business Server-Topologie-Generator.
    
2. Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus einer vorhandenen Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.
    
3. Geben Sie im Dialogfeld **Topologie speichern unter** einen Namen für Ihr Topologiedokument (z. B. **PreWebAppsServerTopology**) in **Dateiname** ein, und klicken Sie dann auf **Speichern**. Diese Topologie kann später wieder abgerufen und neu veröffentlicht werden, falls es zu Problemen kommt.
    
4. Erweitern Sie im Topologie-Generator **Skype for Business Server,** erweitern Sie den Namen Ihres Standorts, erweitern Sie **die Enterprise Edition-Front-End-Pools,** klicken Sie mit der rechten Maustaste auf den Namen eines Ihrer Pools, und klicken Sie dann auf Eigenschaften **bearbeiten.**
    
5. Suchen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Überschrift **Office Web Apps-Server zuordnen**, und klicken Sie dann auf **Neu** (oder wählen Sie in der Dropdownliste einen vorhandenen Office Web Apps-Server aus).
    
6. Geben Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** den vollqualifizierten Domänennamen (FQDN) Ihres Office Web Apps-Servercomputers im Feld **FQDN von Office Web Apps-Server** ein. Anschließend sollte im Feld **Office Web Apps-Server-Such-URL** automatisch die Such-URL Ihres Office Web Apps-Servers stehen.
    
   - Wenn der Office Web Apps Server lokal und in derselben Netzwerkzone wie Skype for Business Server installiert ist, sollte die Option Office Web Apps Server in einem externen Netzwerk (d. h. **Umkreis/Internet)** nicht ausgewählt werden.
    
   - Wenn der Office Web Apps-Server außerhalb Ihrer internen Firewall bereitgestellt ist, aktivieren Sie die Option **Office Web Apps-Server ist in einem externen Netzwerk (d. h. Umkreis/Internet) bereitgestellt**.
    
7. Klicken Sie im Dialogfeld **Neuen Office Web Apps-Server definieren** auf **OK**, und klicken Sie dann auf **OK** im Dialogfeld **Eigenschaften bearbeiten**. Die Ermittlungs-URL wird dann als eine der Zuordnungen des Pools aufgeführt.
    
Sie müssen diese Schritte für jeden Pool wiederholen, der Ihrem Office Web Apps-Server zugeordnet werden soll.
  
Nachdem Sie die Discovery-URL zur Topologie hinzugefügt haben, müssen Sie die aktualisierte Topologie veröffentlichen. Gehen Sie dazu im Topologie-Generator wie folgt vor:
  
1. Klicken Sie auf **Aktion**, und klicken Sie dann auf **Topologie veröffentlichen**.
    
2. Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.
    
3. Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.
    
4. Schließen Sie den Topologie-Generator.
    
## <a name="configure-access-for-external-users"></a>Konfigurieren des Zugriffs für externe Benutzer

Wenn Externe Benutzer (d. h. Benutzer, die sich außerhalb der Firewall Ihrer Organisation anmelden) Zugriff auf Office Web Apps Server -PowerPoint-Präsentationen haben sollen, müssen Sie Office Web Apps Server und einen Reverseproxyserver verwenden. Außerdem müssen Sie eine Websiteveröffentlichungsregel erstellen und konfigurieren, mit der sichergestellt wird, dass Benutzer eine Verbindung mit dem Server herstellen können. 
  
## <a name="validate-the-configuration"></a>Überprüfen der Konfiguration

Nachdem Office Web Apps Server der Topologie hinzugefügt und diese Topologie veröffentlicht wurde, sollten zwei neue Ereignisprotokollereignisse im Skype for Business Server-Ereignisprotokoll angezeigt werden. Zunächst sollte ein LS Data #A0 (Ereignis-ID 41034) hinzugefügt werden. Dieses Ereignis berichtet, dass der Office Web Apps Server ermittelt wurde:
  
 **Der Webkonferenzserver Office Web Apps Server wird ermittelt, der Inhalt von PowerPoint ist aktiviert.**
  
Darüber hinaus sollte ein weiteres LS Data MCU-Ereignis (Ereignis-ID 41032) angezeigt werden, das Office Web Apps Server-URLs zurück meldet. Sie sollten z. B. einen ähnlichen Artikel wie den folgenden sehen:
  
 **Die Ermittlung des Webkonferenzservers office Web Apps Server war erfolgreich.**
  
 **Interne Presenterseite von Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed=**
  
 **Interne Teilnehmerseite für Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp ;embed=true&amp;=**
  
Wenn Sie den Zugriff für externe Benutzer konfiguriert haben, sehen Sie auch etwas ähnliches wie:
  
 **Externe Presenterseite von Office Web Apps Server: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0&amp ;embed**
  
 **Interne Teilnehmerseite für Office Web Apps Server: <https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0&amp;embed=true&amp> ;**
  
Wenn ein LS Data -MCU-Ereignis mit der Ereignis-ID 41033 angezeigt wird, bedeutet dies, dass die Office Web Apps Server-Ermittlung fehlgeschlagen ist. In diesem Fall versucht Skype for Business Server so oft wie nötig, den neu konfigurierten Office Web Apps Server zu ermitteln. Wenn der Ermittlungsprozess wiederholt fehlschlägt, sollten Sie Office Web Apps Server aus dem Topologiedokument entfernen, die aktualisierte Topologie veröffentlichen und dann versuchen, Office Web Apps Server wieder zur Topologie zu hinzufügen, nachdem die Konnektivitätsprobleme behoben wurden.
  
Wenn Office Web Apps Server anscheinend ordnungsgemäß konfiguriert ist und vom Ermittlungsprozess erkannt wurde, können Sie überprüfen, ob Office Web Apps Server wie erwartet funktioniert, indem Sie eine PowerPoint-Präsentation zwischen zwei Skype for Business-Clients freigeben. Wenn Benutzer A die PowerPoint-Präsentation laden und anzeigen kann und Benutzer B dann an der Besprechung teilnehmen und diese Präsentation sehen kann, funktioniert Office Web Apps Server.
  
Auch wenn Office Web Apps Server anscheinend ordnungsgemäß konfiguriert ist, könnte die Fehlermeldung "Einige Freigabefunktionen sind aufgrund von Serverkonnektivitätsproblemen nicht verfügbar" angezeigt werden, wenn Sie versuchen, eine PowerPoint-Präsentation zu teilen. Wenn diese Fehlermeldung angezeigt wird, sollten Sie den Front-End-Server (oder die Server), der dem neuen Office Web Apps Server zugeordnet ist, neu starten.
  

