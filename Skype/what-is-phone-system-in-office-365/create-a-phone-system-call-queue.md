---
title: "Erstellen einer Telefonsystem Anruf Warteschlange"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061

description: "Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. "
---

# Erstellen einer Telefonsystem Anruf Warteschlange

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
Telefon Anruf Systemwarteschlangen einschließen Grußformeln, die verwendet werden, wenn Sie angerufen werden in eine Telefonnummer für Ihre Organisation, die Möglichkeit, automatisch Anrufe parken, und suchen Sie für den nächsten verfügbaren Anruf Agent zum Bearbeiten Sie den Anruf, während Sie die Personen, die Anruf sind Anhören von Musik in der Warteschleife. Sie können einen Anruf einzelnen oder mehrere Warteschlangen für Ihre Organisation erstellen.
  
Telefon Anruf Systemwarteschlangen bereitstellen können:
  
- Eine Begrüßung der Organisation
    
- Musik, während die wartenden Anrufer gehalten werden
    
- Umleitung von Anrufen an Telefonisten in die von E-Mail-aktivierten Verteilerlisten und Sicherheitsgruppen
    
- Erstellen von Einstellungen für die max. Größe von Anrufwarteschleifen, für Timeouts und für Anrufbehandlungsoptionen
    
Personen, die eine Telefonnummer anrufen, für die eine Anrufwarteschleife eingerichtet ist, hören zuerst eine Begrüßung (sofern eine eingerichtet ist). Anschließend werden sie in die Warteschleife eingereiht und warten auf den nächsten verfügbaren Telefonisten. Während die wartenden Anrufer gehalten werden, hören sie Musik. Die Anrufe werden den Telefonisten nach dem  *FIFO*  -Prinzip (First In, First Out) angeboten.
  
Alle in der Warteschleife wartenden Anrufe werden in einem Weiterleitungsmodus an die Telefonzentralen verteilt:
  
- Der erste Anruf in der Warteschleife klingelt bei allen Telefonisten gleichzeitig.
    
    > [!NOTE]
    > Telefonisten, die **offline** sind oder ihren Anwesenheitsstatus auf **Nicht stören** festgelegt haben, werden nicht angerufen.
  
- Es wird nur jeweils eine Benachrichtigung über einen eingehenden Anruf (für den ersten Anruf in der Warteschleife) an die Telefonisten gesendet.
    
- Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.
    
## Schritt 1 - Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:
  
- Ihre Organisation muss eine Lizenz für Enterprise E3 plus **Telefonsystem** oder eine Lizenz für Enterprise E5 (mindestens) verfügen. Die Anzahl der **Telefonsystem** Benutzerlizenzen, die zugewiesen werden Nachteile, dass die Anzahl der Dienst, die Zahlen stehen für Warteschlangen Anruf verwendet werden soll. Die Anzahl der Anruf Warteschlangen, die Sie haben, können ist abhängig von der Anzahl der Lizenzen ein **Telefonsystem** und **Audio Konferenzen**, die in Ihrer Organisation zugewiesen werden. Weitere Informationen zur Lizenzierung, wechseln Sie [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Umgeleitet Anrufe an Personen in Ihrer Organisation, die Online sind, sie müssen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert werden oder Office 365-Plänen aufrufen. Finden Sie unter[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Wenn sie für Enterprise-VoIP aktivieren möchten, können Sie Windows PowerShell verwenden. Führen Sie zum Beispiel:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Weitere Informationen zum Aufrufen von Office 365-Pläne finden Sie unter [Was sind Anrufpläne in Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) und[Anrufpläne für Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)
    
    > [!NOTE]
    > Lokal mit Skype for Business Server 2015 oder Lync Server 2013 und 2010 gehostete Benutzer werden als Telefonisten für Anrufwarteschleifen nicht unterstützt. 
  
- Sie können nur eine gebührenpflichtige zuweisen, und gebührenfreie Service Telefonnummern zu erhalten, haben Sie die **Skype für Business Administrationscenter** oder von einem anderen Dienstanbieter zur Telefonsystem übertragen rufen Sie Warteschlangen. Zum Abrufen und gebührenfreie Service Zahlen verwenden, müssen Sie Kommunikation Gutschriften einrichten. Wenn Sie die Anruf Warteschlange, eine PSTN-Nummer (und nicht den Anruf an einen Benutzer weiterleiten) einwählen möchten, werden auch ausgehende PSTN-Anrufe belastet, pro Minute mit Kommunikation Gutschriften unabhängig davon, ob der ausgehende Anruf zu einer nationalen oder internationale Rufnummer ist. Hierzu finden Sie unter[Was ist Guthaben für Kommunikationen?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) und[Einrichten von Guthaben für Kommunikationen für Ihre Organisation](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!NOTE]
    > Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden. 
  
- Wenn Sie der eingehende Anrufe aus einem Telefonsystem Anruf Warteschlange verteilen, werden diese Clients für Anruf-Agents unterstützt:
    
  - Desktopclient von Skype for Business 2016 (32- und 64-Bit-Version)
    
  - Desktopclient von Lync 2013 (32- und 64-Bit-Version)
    
  - Alle für Skype for Business Online unterstützten IP-Telefonmodelle. Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype für Business-Client (Version 16.8.196 und höher)
    
  - Android Skype für Business-Client (Version 6.16.0.9 und höher)
    
  - iPhone Skype für Business-Client (Version 6.16.0 und höher)
    
  - iPad Skype für Business-Client (Version 6.16.0 und höher)
    
## Schritt 2 - Beziehen oder Übertragen von gebührenpflichtigen oder gebührenfreien Servicenummern

Bevor Sie Ihre Anrufwarteschleifen erstellen und einrichten können, müssen Sie sich gebührenpflichtige oder gebührenfreie Servicenummern besorgen oder entsprechende vorhandene Nummern übertragen. Wenn Sie die gebührenpflichtigen oder gebührenfreien Servicenummern haben, werden diese im **Skype for Business Admin Center** unter **VoIP** auf der Registerkarte **Telefonnummern** angezeigt, und als **Nummerntyp** ist **Service - gebührenfrei** angegeben. Wie Sie Ihre Servicenummern erhalten, erfahren Sie unter[Abrufen von Skype for Business-Leistungsnummern](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md). Wenn Sie eine vorhandene Servicenummer übertragen möchten, lesen Sie [Übertragen von Telefonnummern zu Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA befinden, können Sie Servicenummern nicht über das Skype for Business Admin Center beziehen. Lesen Sie stattdessen [Verwalten von Telefonnummern für Ihre Organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) nach, wie Sie außerhalb der USA vorgehen müssen.
  
## Schritt 3 - Erstellen einer neuen Anrufwarteschleife

Klicken Sie im **Skype for Business Admin Center** auf **Anrufweiterleitung** > **Anrufwarteschleifen** und dann auf **Neu hinzufügen**:
  
### Festlegen des Anzeigenamens, der Telefonnummer und gegebenenfalls der Domäne für die Anrufwarteschleife

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Name**: Geben Sie einen aussagekräftigen Anzeigenamen für die Anrufwarteschleife ein. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten.  <br/> Dieser Name wird in der Benachrichtigung über den eingehenden Anruf angezeigt.  <br/> |
|**2** <br/> |**Telefonnummer** Wählen Sie eine gebührenpflichtige oder gebührenfreie Servicenummer für die Anrufwarteschleife aus. Diese Angabe ist erforderlich. <br/> Wenn keine Servicenummern aufgelistet sind, müssen Sie sich diese besorgen, damit Sie diese Anrufwarteschleife erstellen können. Wie Sie Ihre Servicenummern erhalten, erfahren Sie unter [Abrufen von Skype for Business-Leistungsnummern](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md).  <br/> |
|**3** <br/> |**Domäne**: Wenn diese Option verfügbar ist, wählen Sie die Office 365-Domäne aus, die Sie verwenden möchten. Diese Option ist nur verfügbar, wenn Sie mehrere Domänen für Office 365 verwenden. Wenn mehrere Domänen vorhanden sind, müssen Sie den Domänennamen in der Liste auswählen.  <br/> Ihre Domäne könnte beispielsweise so heißen:  _contoso.com or redmond.contoso.com_ <br/> |
   
### Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Begrüßung** ist optional. Dabei handelt es sich um die Musik, die für Anrufer wiedergegeben wird, die sich in der Anrufwarteschleife befinden. <br/> Sie können eine Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen.  <br/> |
|**2** <br/> |**Wartemusik**: Sie können die Standardwartemusik verwenden, die für die Anrufwarteschleife bereitgestellt wird, oder Sie können eine Audiodatei im WAV-, MP3- oder WMA-Format hochladen und diese als benutzerdefinierte Wartemusik verwenden.  <br/> |
   
### Hinzufügen von Telefonisten zu einer Anrufwarteschleife

![Set up call queues.](../images/9c0c551b-218b-4268-9b73-c85000c99296.png)
  
|||
|:-----|:-----|
|**1** <br/> | Telefonisten (maximal 50) können Folgendes sein: <br/>  Eine Online-Benutzer mit einer Lizenz **Telefonsystem** und Aufrufen planen haben oder für Enterprise-VoIP aktiviert werden. <br/> > [!NOTE]>  Um umzuleiten Anrufe an Personen in Ihrer Organisation, die Online sind, sie müssen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert werden oder aufrufen planen. Finden Sie unter[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Wenn sie für Enterprise-VoIP aktivieren möchten, können Sie Windows PowerShell verwenden. Führen Sie zum Beispiel:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`           Online-Benutzer mit einer mit einer Lizenz **Telefonsystem** oder eine aufrufen planen, die eine e-Mail-Verteilerliste oder Sicherheitsgruppe hinzugefügt werden. Es kann bis zu 30 Minuten dauern, für einen neuen Agent für eine Verteilerliste oder zum Empfangen von Anrufen aus einer Warteschlange Anruf beginnen einer Sicherheitsgruppe hinzugefügt. Eine neu erstellte Liste oder Sicherheit Verteilergruppe kann mit Anruf Warteschlangen zu verwendende verfügbar wird bis zu 48 Stunden dauern. <br/> > [!NOTE]>  Office 365 (moderne Gruppen) können nicht mit Anruf Warteschlangen verwendet werden.          > [!NOTE]>  Lokal mit Skype for Business Server 2015 oder Lync Server 2013 und 2010 gehostete Benutzer werden nicht unterstützt.          |
   
### Festlegen der maximalen Warteschleifengröße und der maximalen Wartezeit

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt. Der Standardwert ist „50", möglich ist jedoch ein Bereich von 0 bis 200.  <br/> Wenn dieses Limit erreicht ist, wird der Anruf gemäß Ihrer Angabe für die Einstellung **Wenn die maximale Anzahl der Anrufe erreicht ist** (siehe unten) behandelt. <br/> |
|**2** <br/> |**Wenn die maximale Anzahl der Anrufe erreicht ist**: Wenn die maximale Größe der Warteschleife erreicht ist (die Sie mit der Einstellung **Maximale Anrufe in der Warteschlange** festgelegt haben), können Sie auswählen, was mit neuen eingehenden Anrufen geschehen soll. <br/> **Mit Besetztzeichen trennen**: Der Anruf wird getrennt.  <br/> **Weiterleiten an**: Wenn Sie diese Einstellung auswählen, haben Sie die folgenden Optionen:  <br/> **Person, die in Ihrem Unternehmen** Eine Online-Benutzer mit einer Lizenz **Telefonsystem** und Aufrufen planen haben oder für Enterprise-VoIP aktiviert werden. Sie können es einrichten, sodass die Person, die Aufrufen an die Voicemail gesendet werden kann. Wählen Sie eine **Person in Ihrem Unternehmen** hierfür, und diese Person haben ihre Anrufe direkt an die Voicemail weitergeleitet. <br/> > [!NOTE]>  Lokal mit Skype for Business Server 2015 und Lync Server 2013 und 2010 gehostete Benutzer werden nicht unterstützt.          **Anrufwarteschleife**: Sie müssen vorher eine weitere Anrufwarteschleife erstellen, die Sie dann hier auswählen können.  <br/> **Automatische Telefonzentrale** Sie müssen bereits erstellt haben eine automatische Telefonzentrale, aber nachdem Sie ausführen möchten, wählen Sie die automatische Telefonzentrale. Finden Sie unter[Einrichten einer automatischen Telefonzentrale für Telefonsystem](set-up-a-phone-system-auto-attendant.md).  <br/> |
|**3** <br/> |**Wie lange ein Anruf in der Warteschlange warten kann**: Sie können auch entscheiden, wie lange ein Anruf in der Warteschleife gehalten werden kann, bis es zu einem Timeout kommt und der Anruf umgeleitet werden muss. Wohin der Anruf umgeleitet wird, hängt von Ihrer Einstellung für **Wenn das Zeitlimit eines Anrufs überschritten ist** ab. Sie können eine Dauer von 0 bis 45 Minuten festlegen. <br/> |
|**4** <br/> |**Wenn das Zeitlimit eines Anrufs überschritten ist**: Wenn der Anruf das Limit erreicht, das Sie für die Einstellung **Wie lange ein Anruf in der Warteschlange warten kann** festgelegt haben, können Sie auswählen, was mit den in der Anrufwarteschleife wartenden Anrufen geschieht: <br/> **Trennen**: Der Anruf wird getrennt.  <br/> **Weiterleiten an**: Wenn Sie diese Einstellung auswählen, haben Sie die folgenden Optionen:  <br/> **Person, die in Ihrem Unternehmen** Eine Online-Benutzer mit einer Lizenz **Telefonsystem** und Pläne aufrufen haben oder für Enterprise-VoIP aktiviert werden. Sie können es einrichten, sodass die Person, die Aufrufen an die Voicemail gesendet werden kann. Wählen Sie eine **Person in Ihrem Unternehmen** hierfür, und diese Person haben ihre Anrufe direkt an die Voicemail weitergeleitet. <br/> > [!NOTE]>  Lokal mit Skype for Business Server 2015 und Lync Server 2013 und 2010 gehostete Benutzer werden nicht unterstützt.          **Anrufwarteschleife**: Sie müssen vorher eine weitere Anrufwarteschleife erstellen, die Sie dann hier auswählen können.  <br/> **Automatische Telefonzentrale** Sie müssen bereits erstellt haben eine automatische Telefonzentrale, aber nachdem Sie ausführen möchten, wählen Sie die automatische Telefonzentrale. Finden Sie unter[Einrichten einer automatischen Telefonzentrale für Telefonsystem](set-up-a-phone-system-auto-attendant.md).  <br/> |
   
## Ändern des Benutzers Anrufer-ID, um einen Anruf-Warteschlange Telefonnummer werden

Sie können Identität des Benutzers ändern ihre Anrufer-ID für ausgehende Anrufe an eine Warteschlange Anruf stattdessen durch Erstellen einer Richtlinie mithilfe des Cmdlets **New-CallingLineIdentity** schützen.
  
In dieser Instanz gehen Sie wie folgt:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Wenden Sie die Richtlinie für den Benutzer mithilfe des Cmdlets **Grant-CallingLineIdentity**. In dieser Instanz gehen Sie wie folgt:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Sie erhalten weitere Informationen zum Anrufer-ID-Einstellungen in Ihrer Organisation ändern [Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.
  
### Cmdlets für Anrufwarteschleifen

Zum Verwalten einer Anrufwarteschleife benötigen Sie die folgenden Cmdlets.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### Weitere Informationen zu Windows PowerShell

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

