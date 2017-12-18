---
title: "Einrichten Ihres Netzwerks für Skype-Livekonferenz"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
description: "Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees."
---

# Einrichten Ihres Netzwerks für Skype-Livekonferenz

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
Nach der [Aktivieren von Skype-Livekonferenz](enable-skype-meeting-broadcast.md) Skype-Livekonferenz müssen Sie Ihr Netzwerk konfigurieren. Führen Sie diesen Schritt aus, wenn Sie Webinare und andere Konferenzen für Personen außerhalb Ihres Unternehmens durchführen möchten.
  
Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.
  
Wenn Sie diesen Schritt überspringen und eine andere Business stattdessen zu Ihrem Föderation hinzufügen, damit Sie in Broadcasts eingeladen werden können, folgen Sie den Schritten [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## Schritt 1: Einrichten von zulässigen Domänen

Verwenden Sie **eine** der folgenden Methoden, um zulässige Domänen einzurichten:
  
### 

 **Methode 1: Verwenden des Office 365 Admin Center**
  
1. Wechseln Sie zum **Office 365-Verwaltungskonsole**, und klicken Sie dann im linken Navigationsbereich, klicken Sie auf **Einstellungen** > **Dienste und -add-ins**, und wählen Sie dann **Skype for Business**.
    
2. Wählen Sie auf der Seite **externe Freigabe** unter **Domäne Ausnahmen** aus, **werden alle Domänen mit Ausnahme blockiert**, und geben Sie die folgenden Domänen, die durch ein Semikolon (;) getrennt sind:
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. Klicken Sie auf **Speichern**.
    
### 

 **Methode 2: Verwenden von Windows PowerShell**
  
- Klicken Sie im **Menü Start** mit der rechten Maustaste in **Windows PowerShell**, und klicken Sie auf **als Administrator ausführen**. Geben Sie in der **Windows PowerShell**-Fenster jede Zeile, und drücken Sie die EINGABETASTE.
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## Schritt 2: Hinzufügen von Skype-Besprechung übertragen Domänen, URLs und IP-Adressen

Im zweiten Schritt des Setupvorgangs fügen Sie zuerst die benötigten Domänen hinzu. Anschließend fügen Sie die IP-Adressen und URLs hinzu, die erforderlich sind, damit Skype-Livekonferenz funktioniert.
  
- **Fügen Sie die erforderlichen Domänenendpunkte hinzu:**
    
    Wenn Skype Meeting Broadcast verwendet werden soll, muss der Zugriff auf folgende Endpunkte für Clientcomputer möglich sein.
    
|
|
|**Zeile**|**Zweck**|**Quelle | Anmeldeinformationen**|**Ziel**|**ExpressRoute für Office 365 BGP-Communitys**|**CIDR-Adresse**|**Port**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |**Erforderlich:** Skype for Business-Endpunkte. <br/> |Lesen Sie [Skype for Business Online](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO), und stellen Sie sicher, dass auf alle Einträge mit der Bezeichnung "erforderlich" zugegriffen werden kann.  <br/> ||||
|2  <br/> |**Erforderlich:**[Skype Meeting Broadcast](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)-Referent und -Teilnehmer  <br/> |Clientcomputer/angemeldeter Benutzer  <br/> |
```
*.broadcast.skype.com
broadcast.skype.com
browser.pipe.aria.microsoft.com

```

|Ja  <br/> |[](8548a211-3fe7-47cb-abb1-355ea5aa88a2.md#BKMK_SfB_IP).  <br/> |TCP 443  <br/> |
|3  <br/> |**Erforderlich:**[Skype Meeting Broadcast](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)-Referent und -Teilnehmer  <br/> |Clientcomputer/angemeldeter Benutzer  <br/> |
```
aka.ms
amp.azure.net

```

|Nein  <br/> |N/V  <br/> |TCP 443  <br/> |
|4  <br/> |**Erforderlich:**[Skype Meeting Broadcast](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)-Referent und -Teilnehmer (einschließlich CDNs)  <br/> |Clientcomputer/angemeldeter Benutzer  <br/> |
```
*.keydelivery.mediaservices.windows.net
*.msecnd.net
*.streaming.mediaservices.windows.net
ajax.aspnetcdn.com
mlccdn.blob.core.windows.net

```

|Nein  <br/> |N/V  <br/> |TCP 443  <br/> |
   
- **Fügen Sie die erforderlichen URLs und IP-Adressen für Skype for Business Online-Endpunkte hinzu, die Sie**[hier](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo) finden.
    
## Einrichten von Skype-Livekonferenz in Hybridbereitstellungen und -organisationen

Wenn Sie verfügen über eine Organisation Skype for Business Online und einer lokalen Bereitstellung von Lync Server 2010, Microsoft Lync Server 2013 und Skype for Business Server 2015 haben Sie beide Benutzer online und lokale, Setupschritte andere, die Sie darüber hinaus mit denen aktivieren oben ausführen müssen Ihre Organisation der lokalen zur Kommunikation mit Skype for Business Online und alle Benutzer kann zum Erstellen und teilnehmen an einer Skype Meeting Broadcast zulassen. Was sind, dass diese Anforderungen finden Sie unter [Konfigurieren der lokalen Bereitstellung für Skype Besprechung übertragen](https://go.microsoft.com/fwlink/?LinkId=617070).
  
## Verwandte Themen

[Aktivieren von Skype-Livekonferenz](enable-skype-meeting-broadcast.md)
  
[URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

