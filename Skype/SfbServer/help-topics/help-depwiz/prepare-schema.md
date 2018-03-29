---
Titel: "Schema vorbereiten" ms.author: Jambirk Autor: Jambirk Manager: Serdars ms.date: 2/8/2018 ms.audience: IT-Experten ms.topic: f1_keywords Artikel:
- ms.lync.dep.DeployMainSchemaPrep ms.prod: Skype für Business Itpro Localization_priority: normalen ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c Beschreibung: ", um das Schema für Active Directory-Domänendienste vorbereiten, ausführen das Schema vorbereiten Schritt in der Skype für Business Server-Bereitstellungs-Assistenten. Klicken Sie auf Ausführen, um die Vorbereitung des Schemas beginnen. Im Schritt „Schema vorbereiten“ werden die bereitgestellten Schemadefinitionsdateien im Verzeichnis „\Programme\Microsoft Lync Server 2013\Deployment\Setup“ des Systems gelesen, auf dem der Bereitstellungs-Assistent ausgeführt wird. Diese Dateien stehen auch auf den Installationsmedien im Verzeichnis „\Support\Schema“ zur Verfügung. Der Schritt „Schema vorbereiten“ dient zum Erweitern des Schemas und zum Melden des Prozessstatus. Ferner wird in diesem Schritt der Abschluss des Prozesses gemeldet. Auf dem Zusammenfassungsbildschirm können Sie die Protokolle des Prozesses überprüfen. Überprüfen Sie die Protokolle, um sicherzustellen, dass die Vorbereitung der abgeschlossenen und erfolgreichen Sendevorgang war."
---

# <a name="prepare-schema"></a>Vorbereiten des Schemas
 
Führen Sie zur Vorbereitung des Schemas für Active Directory Domain Services im Schema vorbereiten Schritt in der Skype für Business Server-Bereitstellungs-Assistenten auf. Klicken Sie auf **Ausführen**, um mit der Schemavorbereitung zu beginnen. Im Schritt „Schema vorbereiten“ werden die bereitgestellten Schemadefinitionsdateien im Verzeichnis „\Programme\Microsoft Lync Server 2013\Deployment\Setup“ des Systems gelesen, auf dem der Bereitstellungs-Assistent ausgeführt wird. Diese Dateien stehen auch auf den Installationsmedien im Verzeichnis „\Support\Schema“ zur Verfügung. Der Schritt „Schema vorbereiten“ dient zum Erweitern des Schemas und zum Melden des Prozessstatus. Ferner wird in diesem Schritt der Abschluss des Prozesses gemeldet. Auf dem Zusammenfassungsbildschirm können Sie die Protokolle des Prozesses überprüfen. Vergewissern Sie sich mithilfe der Protokolle, dass die Vorbereitung erfolgreich abgeschlossen wurde.
  
> [!IMPORTANT]
> Zum Erweitern des Schemas müssen Sie bei der Domäne als Mitglied der Gruppen „Schema-Admins“ und „Organisations-Admins“ angemeldet sein. 
  
Zum Erweitern des Schemas Active Directory Domain Services zur Unterstützung von Skype für Business Server 2015 Server Service und User-Objekte werden Klassen und Attribute hinzugefügt. Vor dem Erweitern des Schemas müssen Sie eine Systemstatussicherung des Domänencontrollers mit der Schemamasterrolle ausführen. Ausführliche Informationen zu den Sicherungsvorgang für Windows Server 2008 R2 mit SP1, finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198). Windows Server 2003 und Windows Server 2003 R2 finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).
  
> [!CAUTION]
> Das Erweitern des Schemas ist nicht umkehrbar. Versuchen Sie immer, die potenziellen Auswirkungen einer fehlerhaften Schemaerweiterung einzudämmen und sicherzustellen, dass die Erweiterung des Schemas erfolgreich ist. Dies ist besonders bei einem Ausfall der Kommunikation oder einem anderen Ausfall auf dem Server wichtig. Sie sollten eine Sicherung der Schemamaster-Domänencontroller und eine vollständige Sicherung von Active Directory ausführen. 
  
So führen Sie eine Sicherung der Schemamaster-Domänencontroller und eine vollständige Sicherung der Active Directory aus:
  
1. Trennen Sie den Domänencontroller mit der Schemamasterrolle vom Netzwerk.
    
2. Führen Sie eine Systemstatussicherung des Domänencontrollers mit dem Schemamaster durch.
    
3. Erweitern Sie das Schema.
    
4. Verbinden Sie den Domänencontroller nach erfolgreicher Schemaerweiterung wieder mit dem Netzwerk und stellen Sie sicher, dass die Replikation aktiv und betriebsbereit ist.
    
5. Wiederherstellen von in unwahrscheinlichen bei einem den Systemen Zustand des Domänencontrollers und Active Directory anhand der Systemstatus-Sicherung, die Sie zuvor erstellt haben.
    
> [!NOTE]
> Wenn Sie die Protokolldateien überprüfen, die durch die Skype für Business Server-Bereitstellungs-Assistenten erstellt werden müssen, finden Sie die Dateien auf dem Computer, auf dem Bereitstellungs-Assistenten ausgeführt wurde, im Verzeichnis Benutzer der Active Directory-Benutzer, die im Schritt ausgeführt hat. Angenommen, wenn der Benutzer als Domänenadministrator in der Domäne Contoso.net angemeldet, die Protokolldateien befinden sich im: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

