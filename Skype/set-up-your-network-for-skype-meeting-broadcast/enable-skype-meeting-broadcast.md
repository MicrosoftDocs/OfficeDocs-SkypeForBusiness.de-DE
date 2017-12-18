---
title: "Aktivieren von Skype-Livekonferenz"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
description: "Bevor Sie die Personen in Ihrer Organisation Skype Meeting Broadcast verwenden können, müssen Sie es aktivieren. Dazu müssen Sie wissen, wie Sie Windows PowerShell verwenden möchten. Wenn Sie nicht, dass Windows PowerShell wissen, erwägen Sie das Einstellen von einem Microsoft-Partner , führen Sie diesen Schritt für Sie."
---

# Aktivieren von Skype-Livekonferenz

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
Bevor Sie die Personen in Ihrer Organisation Skype Meeting Broadcast verwenden können, müssen Sie es aktivieren. Dazu müssen Sie wissen, wie Sie Windows PowerShell verwenden möchten. Wenn Sie nicht, dass Windows PowerShell wissen, erwägen Sie das Einstellen von einem [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) , führen Sie diesen Schritt für Sie.
  
> [!CAUTION]
> Skype Meeting Broadcast ist standardmäßig deaktiviert, weil Verteilung des Inhalts einer übertragenen Besprechung Medien des Microsoft Azure Content Delivery Network (CDN) verwendet, um sehr hoch skalierbar für die Unterstützung von mehreren Tausend Betrachtern einer übertragen zu erzielen. Die aufgeteilter Medieninhalten das CDN passiert ist verschlüsselt und der Cache CDN hat eine beschränkte Lebensdauer. Die Komponente Azure CDN möglicherweise auch nicht noch nicht alle Elemente aus der EU-Richtlinie zum Schutz Daten Wortstamm EU Modell Klauseln gerecht. Aktivieren Sie dieses Feature, bestätigen Sie diese Mitteilung an. 
  
## Aktivieren von Skype-Livekonferenz im Skype for Business Admin Center

1. Melden Sie sich mit dem Konto Globaler Office 365-Administrator bei [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) an.
    
2. Navigieren Sie im „Office 365 Admin Center" zu **Admin Center** > **Skype for Business**.
    
3. Die **Skype für Business Administrationscenter**, wechseln Sie zur **onlinebesprechungen** > **Besprechungen übertragen**, und wählen Sie dann **Aktivieren von Skype-Besprechung übertragen**.
    
## Aktivieren von Skype-Livekonferenz mit PowerShell

1. Überprüfen Sie, ob Sie Version 3.0 oder höher von Windows PowerShell ausführen.
    
1. So überprüfen Sie, ob Sie Version 3.0 oder höher benutzen: **Startmenü** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie  _Get-Host_ in das **Windows PowerShell**-Fenster eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
2. Wählen Sie im **Menü Start** **Windows PowerShell** aus.
    
3. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
  ```
  $Credential = get-credential
  ```

  ```
  $O365Session = New-CsOnlineSession -Credential $credential
  ```

  ```
  Import-PSSession $O365Session
  ```

4. Bestätigen Sie Ihre aktuelle Skype Meeting Broadcast-Konfiguration, indem Sie Folgendes ausführen:
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Überprüfen Sie, ob der Parameter  _EnableBroadcastMeeting_ auf `False` festgelegt ist.
    
     ![Cmdlet "Enable Organization" in Skype Meeting Broadcast](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Aktivieren Sie Skype Meeting Broadcast für Ihr Unternehmen, indem Sie Folgendes ausführen:
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    Sie können bestätigen, dass die Einstellung aktiviert ist, indem Sie  `Get-CsBroadcastMeetingConfiguration` erneut ausführen.
    
     ![Cmdlet "Enable Organization" in Skype Meeting Broadcast](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Nach der Änderung kann es bis zu einer Stunde dauern, bis sie im Skype Meeting Broadcast-Portal angezeigt wird. 
  
6. Die Benutzer können jetzt übertragenen Besprechungen mit anderen Benutzern in Ihrem Unternehmen enthalten. Wenn Sie diese Schritte erhalten möchten, zeigen Sie auf diese [Was ist eine Skype-Livekonferenz?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## Konfigurieren Ihres Netzwerks zur Durchführung von Livekonferenzen mit externen Teilnehmern

Wenn Sie über eine Firewall verfügen und Konferenzen mit Personen außerhalb Ihres Unternehmens (die nicht zum Unternehmensverbund gehören) durchführen möchten, müssen Sie Ihr Netzwerk unter Befolgung dieser Anweisungen konfigurieren: [Einrichten Ihres Netzwerks für Skype-Livekonferenz](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.
  
Wenn Sie diesen Schritt überspringen und stattdessen ein anderes Unternehmen zu Ihrem Föderation hinzufügen, finden Sie unter [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
## Siehe auch
<a name="MT_Footer"> </a>

#### Weitere Ressourcen

[Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

