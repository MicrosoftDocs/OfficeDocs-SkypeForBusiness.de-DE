---
title: Stage AV and OAuth certificates in Skype for Business Server using -Roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Zusammenfassung: Stufe von AV- und OAuth-Zertifikaten für Skype for Business Server.'
ms.openlocfilehash: a2586e9ebda1bae1605fd6033681b469e6731b8c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806555"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Stage AV and OAuth certificates in Skype for Business Server using -Roll in Set-CsCertificate
 
**Zusammenfassung:** Stufe Sie AV- und OAuth-Zertifikate für Skype for Business Server ein.
  
Die Audio-/Videokommunikation (A/V) ist eine wichtige Komponente von Skype for Business Server. Features wie Anwendungsfreigabe und Audio- und Videokonferenzen beruhen auf den Zertifikaten, die dem A/V-Edgedienst zugewiesen sind, insbesondere dem A/V-Authentifizierungsdienst.
  
> [!IMPORTANT]
> Dieses neue Feature ist für den A/V-Edgedienst und das OAuthTokenIssuer-Zertifikat konzipiert. Andere Zertifikattypen können zusammen mit dem A/V-Edgedienst und dem OAuth-Zertifikattyp bereitgestellt werden, profitieren jedoch nicht vom Koexistenzverhalten des A/V-Edgedienstzertifikats.
  
Die PowerShell-Cmdlets der Skype for Business Server-Verwaltungsshell, die zum Verwalten von Skype for Business Server-Zertifikaten verwendet werden, beziehen sich auf das A/V-Edgedienstzertifikat als Den Zertifikattyp "AudioVideoAuthentication" und das "OAuthServer"-Zertifikat als "typeOAuthTokenIssuer". Für den Rest dieses Themas und um die Zertifikate eindeutig zu identifizieren, wird auf sie mit demselben Bezeichnertyp verwiesen: "AudioVideoAuthentication" und "OAuthTokenIssuer".
  
Der A/V-Authentifizierungsdienst ist für die Ausgabe von Token zuständig, die von Clients und anderen A/V-Verbrauchern verwendet werden. Die Token werden aus Attributen des Zertifikats generiert, und wenn das Zertifikat abläuft, führen der Verbindungsverlust und die Anforderung zur erneuten Verbindung mit einem neuen Token, das vom neuen Zertifikat generiert wird, zu einem Verlust der Verbindung. Ein neues Feature in Skype for Business Server verringert dieses Problem– die Möglichkeit, ein neues Zertifikat vor ablaufend dem alten auszustellen und zu ermöglichen, dass beide Zertifikate für einen bestimmten Zeitraum weiterhin funktionieren. Dieses Feature verwendet aktualisierte Funktionen im Set-CsCertificate Skype for Business Server Management Shell-Cmdlet. Der neue Parameter "-Roll" mit dem vorhandenen Parameter "-EffectiveDate" legt das neue Zertifikat "AudioVideoAuthentication" im Zertifikatspeicher ab. Das ältere "AudioVideoAuthentication"-Zertifikat bleibt für ausgestellte Token bestehen, für die eine Überprüfung möglich ist. Beginnend mit dem Erstellen des neuen Zertifikats "AudioVideoAuthentication" tritt die folgende Ereignisreihe auf:
  
> [!TIP]
> Mithilfe der Skype for Business Server Management Shell-Cmdlets zum Verwalten von Zertifikaten können Sie separate und unterschiedliche Zertifikate für jeden Zweck auf dem Edgeserver anfordern. Die Verwendung des Zertifikatassistenten im Skype for Business Server-Bereitstellungs-Assistenten  hilft Ihnen beim Erstellen von Zertifikaten, ist jedoch in der Regel vom Standardtyp, der alle für den Edgeserver verwendeten Zertifikate in einem einzigen Zertifikat zusammentützt. Wenn Sie die Funktion für fortlaufende Zertifikate verwenden, wird empfohlen, das Zertifikat "AudioVideoAuthentication" von den anderen Zertifikatzwecken zu entkoppeln. Sie können ein Zertifikat vom Typ "Standard" bereitstellen und bereitstellen, aber nur der Teil "AudioVideoAuthentication" des kombinierten Zertifikats wird vom Staging profitieren. Ein Benutzer, der an einer Sofortnachrichten unterhaltung beteiligt ist, wenn das Zertifikat abläuft, muss sich abmelden und erneut anmelden, um das neue Zertifikat zu verwenden, das dem Zugriffs-Edgedienst zugeordnet ist. Ein ähnliches Verhalten tritt für einen Benutzer auf, der mit dem Webkonferenz-Edgedienst an einer Webkonferenz beteiligt ist. Das OAuthTokenIssuer-Zertifikat ist ein bestimmter Typ, der von allen Servern gemeinsam verwendet wird. Sie erstellen und verwalten das Zertifikat an einem Ort, und das Zertifikat wird im zentralen Verwaltungsspeicher für alle anderen Server gespeichert.
  
Zusätzliche Informationen werden benötigt, um die Optionen und Anforderungen bei der Verwendung des Set-CsCertificate-Cmdlet zum Bereitstellen von Zertifikaten vor dem Ablauf des aktuellen Zertifikats nachvollziehen zu können. Der Parameter "-Roll" ist wichtig, aber im Wesentlichen ein einzelner Zweck. Wenn Sie ihn als Parameter definieren, informieren Sie Set-CsCertificate, dass Sie Informationen über das Zertifikat bereitstellen, das von "-Type" definiert wird (z. B. "AudioVideoAuthentication" und "OAuthTokenIssuer"), wann das Zertifikat wirksam wird, definiert durch "-EffectiveDate".
  
 **-Roll:** Der Parameter "-Roll" ist erforderlich und verfügt über Abhängigkeiten, die zusammen mit ihm bereitgestellt werden müssen. Parameter, die zum Festlegen der betroffenen Zertifikate und ihrer Anwendungsweise erforderlich sind:
  
 **-EffectiveDate**: Der Parameter "-EffectiveDate" definiert, wann das neue Zertifikat mit dem aktuellen Zertifikat gemeinsam aktiv wird. The -EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer time. Ein empfohlenes Minimum von "-EffectiveDate" für das Zertifikat "AudioVideoAuthentication" beträgt 8 Stunden. Dies ist die Standardtokenlebensdauer für AV-Edgediensttoken, die mit dem Zertifikat "AudioVideoAuthentication" ausgegeben werden.
  
Für das Bereitstellen der OAuthTokenIssuer-Zertifikate liegen verschiedene Anforderungen für die Durchlaufzeit vor, bevor das Zertifikat wirksam werden kann. Der Mindestwert des OAuthTokenIssuer-Zertifikats für die Durchlaufzeit sollte 24 Stunden vor der Ablaufzeit des aktuellen Zertifikats betragen. Die erweiterte Durchlaufzeit für die Koexistenz ist durch andere Serverrollen begründet, die von dem OAuthTokenIssuer-Zertifikat (beispielsweise Exchange Server) abhängen, das eine längere Aufbewahrungszeit für durch Zertifikate erstellte Authentifizierungs- und Verschlüsselungsschlüsselelemente besitzt.
  
 **-Thumbprint**: Beim Fingerabdruck handelt es sich um ein für dieses Zertifikat eindeutiges Attribut. Der Parameter "-Thumbprint" wird verwendet, um das Zertifikat zu identifizieren, das von den Aktionen des cmdlets Set-CsCertificate wird.
  
 **-Type:** Der Parameter "-Type" kann einen einzelnen Zertifikatverwendungstyp oder eine durch Kommas getrennte Liste der Zertifikatverwendungstypen akzeptieren. Die Zertifikattypen geben für das Cmdlet und den Server an, worin der Zweck des Zertifikats besteht. Geben Sie beispielsweise "AudioVideoAuthentication" für die Verwendung durch den A/V-Edgedienst und den AUTHENTIFIZIERUNGsdienst ein. Wenn Sie verschiedene Zertifikattypen zum gleichen Zeitpunkt bereitstellen möchten, müssen Sie die längste effektive Mindestdurchlaufzeit für die Zertifikate berücksichtigen. Sie müssen beispielsweise Zertifikate vom Typ "AudioVideoAuthentication" und Typ "OAuthTokenIssuer" bereitstellen. Ihr Minimum -EffectiveDate muss das größere der beiden Zertifikate sein, in diesem Fall OAuthTokenIssuer, das eine Minimale Vorlaufzeit von 24 Stunden hat. Wenn Sie das Zertifikat "AudioVideoAuthentication" nicht mit einer Durchlaufzeit von 24 Stunden bereitstellen möchten, stellen Sie es separat mit einem Ihren Anforderungen entsprechenden Wert für "EffectiveDate" bereit.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein A/V-Edgedienstzertifikat mit den Parametern "-Roll" und "-EffectiveDate"

1. Melden Sie sich als Mitglied der Gruppe Administratoren am lokalen Computer an.
    
2. Fordern Sie eine Verlängerung oder ein neues AudioVideoAuthentication-Zertifikat mit exportierbarem privaten Schlüssel für das vorhandene Zertifikat im A/V-Edgedienst an.
    
3. Importieren Sie das neue Zertifikat "AudioVideoAuthentication" auf den Edgeserver und alle anderen Edgeserver in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben).
    
4. Konfigurieren Sie das importierte Zertifikat mit Set-CsCertificate cmdlet, und verwenden Sie den Parameter "-Roll" mit dem Parameter "-EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden. Dies gibt uns einen Zeitpunkt, zu dem das Zertifikat auf "Aktiv" festgelegt werden muss, und ist "-EffectiveDate \<string\> : "7/22/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Für einen Edgepool müssen alle AudioVideoAuthentication-Zertifikate bereitgestellt und nach dem Datum und der Uhrzeit bereitgestellt werden, die durch den Parameter "-EffectiveDate" des ersten Zertifikats definiert sind, um mögliche Unterbrechungen der A/V-Kommunikation aufgrund des ablaufenden älteren Zertifikats zu vermeiden, bevor alle Client- und Consumertoken mithilfe des neuen Zertifikats erneuert wurden. 
  
    Der Set-CsCertificate befehl mit dem Parameter "-Roll" und "-EffectiveTime":
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Ein Set-CsCertificate-Beispielbefehl:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > Das EffectiveDate muss so formatiert sein, dass es den Regionen- und Spracheinstellungen Ihres Servers entsprechen kann. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet. 
  
Um den Prozess weiter zu verstehen, den Set-CsCertificate, -Roll und -EffectiveDate zum Ausstellen eines neuen Zertifikats für die Ausgabe neuer AudioVideoAuthentication-Token verwenden, während weiterhin ein vorhandenes Zertifikat zum Überprüfen von AudioVideoAuthentication verwendet wird, die von Verbrauchern verwendet werden, ist eine visuelle Zeitachse eine effektive Möglichkeit, den Prozess zu verstehen. Im folgenden Beispiel ermittelt der Administrator, dass das A/V-Edgedienstzertifikat am 22.07.2015 um 14:00:00 Uhr abläuft. Er fordert ein neues Zertifikat an und importiert es auf jeden Edgeserver in seinem Pool. Am 22.07.2015 um 02:00 Uhr beginnt er mit der Ausführung von Get-CsCertificate mit "-Roll", "-Thumbprint" entspricht der Fingerabdruckzeichenfolge des neuen Zertifikats und "-EffectiveTime" auf 22.07.2015 06:00:00 Uhr. Er führt diesen Befehl auf jedem Edgeserver aus.
  
![Verwenden der Parameter "Roll" und "EffectiveDate".](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Stufe**|
|:-----|:-----|
|1   <br/> |Start: 22.07.2015 12:00:00  <br/> Das aktuelle AudioVideoAuthentication-Zertifikat läuft am 22.07.2015 um 14:00:00 Uhr ab. Dies wird durch den Ablaufzeitstempel des Zertifikats bestimmt. Planen Sie den Austausch von Zertifikaten und den Rollover so, dass eine Überlappung von 8 Stunden (Standardtokenlebensdauer) berücksichtigt wird, bevor das vorhandene Zertifikat die Ablaufzeit erreicht. Die Vorlaufzeit von 2:00:00 Uhr wird in diesem Beispiel verwendet, um dem Administrator ausreichend Zeit zum Platzieren und Bereitstellen der neuen Zertifikate vor der Ablaufzeit von 6:00:00 Uhr zu geben.  <br/> |
|2   <br/> |22.07.2015 02:00:00 - 22.07.2015 05:59:59  <br/> Legen Sie Zertifikate auf Edgeservern ab 6:00:00 Uhr (4 Stunden Vorlaufzeit in diesem Beispiel, kann aber länger sein) mithilfe von Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate \<datetime string of the effective time for new certificate\>  <br/> |
|3   <br/> |22.07.2015 06:00 - 22.07.2015 14:00  <br/> Um Token zu überprüfen, wird zuerst das neue Zertifikat ausprobiert, und wenn das neue Zertifikat das Token nicht validieren kann, wird das alte Zertifikat ausprobiert. Dieser Prozess wird für alle Token während des Überlappungszeitraums von 8 Stunden (Standardtokenlebensdauer) verwendet.  <br/> |
|4   <br/> |Ende: 22.07.2015 14:00:01  <br/> Das alte Zertifikat ist abgelaufen, und das neue Zertifikat wurde übernommen. Altes Zertifikat kann sicher entfernt werden, wenn Remove-CsCertificate -Type \<certificate usage type\> -Previous  <br/> |
   
Wenn der effektive Zeitpunkt erreicht ist (22.07.2015 06:00:00 Uhr), werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2015 14:00:00 Uhr), werden Token nur vom neuen Zertifikat überprüft. Das alte Zertifikat kann mit dem Cmdlet "Remove-CsCertificate"-Parameter "-Previous" sicher entfernt werden.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein OAuthTokenIssuer-Zertifikat mit den Parametern "-Roll" und "-EffectiveDate"

1. Melden Sie sich als Mitglied der Gruppe Administratoren am lokalen Computer an.
    
2. Fordern Sie eine Verlängerung oder ein neues OAuthTokenIssuer-Zertifikat mit exportierbarem privatem Schlüssel für das vorhandene Zertifikat auf dem Front-End-Server an.
    
3. Importieren Sie das neue OAuthTokenIssuer-Zertifikat auf einen Front-End-Server in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben). Das OAuthTokenIssuer-Zertifikat wird global repliziert und muss auf den Servern in Ihrer Bereitstellung aktualisiert und erneuert werden. Der Front-End-Server wird als Beispiel verwendet.
    
4. Konfigurieren Sie das importierte Zertifikat mit Set-CsCertificate cmdlet, und verwenden Sie den Parameter "-Roll" mit dem Parameter "-EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden. 
    
    Der Set-CsCertificate befehl mit dem Parameter "-Roll" und "-EffectiveTime":
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Ein Set-CsCertificate-Beispielbefehl:
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> Das EffectiveDate muss so formatiert sein, dass es den Regionen- und Spracheinstellungen Ihres Servers entsprechen kann. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet. 
  
Wenn der effektive Zeitpunkt erreicht ist (21.07.2015 01:00:00 Uhr), werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2015 14:00:00 Uhr), werden Token nur vom neuen Zertifikat überprüft. Das alte Zertifikat kann mit dem Cmdlet "Remove-CsCertificate"-Parameter "-Previous" sicher entfernt werden.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Weitere Informationen

[Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
