---
title: Bereitstellen von AV- und OAuth-Zertifikaten in Skype for Business Server mithilfe von "-Roll" in Set-CsCertificate
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Zusammenfassung: Bereitstellen von AV- und OAuth-Zertifikaten für Skype for Business Server.'
ms.openlocfilehash: 7eeac29ba322d40d8ab8f70712ecfca5ead5c97d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832109"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Bereitstellen von AV- und OAuth-Zertifikaten in Skype for Business Server mithilfe von "-Roll" in Set-CsCertificate
 
**Zusammenfassung:** Bereitstellen von AV- und OAuth-Zertifikaten für Skype for Business Server.
  
Audio-/Videokommunikation (A/V) ist eine wichtige Komponente der Skype for Business Server. Features wie Anwendungsfreigabe und Audio- und Videokonferenzen basieren auf den Zertifikaten, die dem A/V-Edgedienst zugewiesen sind, insbesondere dem A/V-Authentifizierungsdienst.
  
> [!IMPORTANT]
> Dieses neue Feature ist für den A/V-Edgedienst und das OAuthTokenIssuer-Zertifikat geeignet. Andere Zertifikattypen können zusammen mit dem A/V-Edgedienst und dem OAuth-Zertifikattyp bereitgestellt werden, profitieren jedoch nicht vom Koexistenzverhalten des A/V-Edgedienstzertifikats.
  
Die powerShell-Cmdlets der Skype for Business Server Verwaltungsshell, die zum Verwalten Skype for Business Server Zertifikate verwendet werden, beziehen sich auf das A/V-Edgedienstzertifikat als AudioVideoAuthentication-Zertifikattyp und das OAuthServer-Zertifikat als TypOAuthTokenIssuer. Für den Rest dieses Themas und um die Zertifikate eindeutig zu identifizieren, werden sie mit demselben Bezeichnertyp, AudioVideoAuthentication undOAuthTokenIssuer, bezeichnet.
  
Der A/V-Authentifizierungsdienst ist für die Ausgabe von Token verantwortlich, die von Clients und anderen A/V-Consumern verwendet werden. Die Token werden aus Attributen auf dem Zertifikat generiert, und wenn das Zertifikat abläuft, gehen die Verbindung und die Anforderung, sich erneut mit einem neuen Token zu verbinden, das vom neuen Zertifikat generiert wird, verloren. Ein neues Feature in Skype for Business Server verringert dieses Problem – die Möglichkeit, ein neues Zertifikat vor dem alten Zertifikat zu bereitstellen, das abläuft, und beide Zertifikate können für einen bestimmten Zeitraum weiterhin funktionieren. Dieses Feature verwendet aktualisierte Funktionen im Cmdlet Set-CsCertificate Skype for Business Server Verwaltungsshell. Der neue Parameter "-Roll" mit dem vorhandenen Parameter "-EffectiveDate" platziert das neue AudioVideoAuthentication-Zertifikat im Zertifikatspeicher. Das ältere AudioVideoAuthentication-Zertifikat bleibt erhalten, damit ausgestellte Token überprüft werden. Ab dem Einfügen des neuen AudioVideoAuthentication-Zertifikats tritt die folgende Ereignisserie auf:
  
> [!TIP]
> Mithilfe der Cmdlets der Skype for Business Server Verwaltungsshell zum Verwalten von Zertifikaten können Sie separate und unterschiedliche Zertifikate für jeden Zweck auf dem Edgeserver anfordern. Die Verwendung des Zertifikat-Assistenten im Skype for Business Server Bereitstellungs-Assistenten unterstützt Sie beim Erstellen von Zertifikaten, ist jedoch in der Regel vom **Standardtyp,** der alle für den Edgeserver verwendeten Zertifikate auf ein einzelnes Zertifikat übergibt. Die empfohlene Vorgehensweise, wenn Sie das Feature für das fortlaufende Zertifikat verwenden, besteht darin, das AudioVideoAuthentication-Zertifikat von den anderen Zertifikatzwecken zu entkoppeln. Sie können ein Zertifikat vom Standardtyp bereitstellen und bereitstellen, aber nur der AudioVideoAuthentication-Teil des kombinierten Zertifikats wird vom Staging profitieren. Ein Benutzer, der an einer Chatunterhaltung beteiligt ist, wenn das Zertifikat abläuft, muss sich abmelden und wieder anmelden, um das neue Zertifikat zu verwenden, das dem Zugriffs-Edgedienst zugeordnet ist. Ein ähnliches Verhalten tritt für einen Benutzer auf, der an einer Webkonferenz mithilfe des Webkonferenz-Edgediensts beteiligt ist. Das OAuthTokenIssuer-Zertifikat ist ein bestimmter Typ, der auf allen Servern gemeinsam verwendet wird. Sie erstellen und verwalten das Zertifikat an einem Ort, und das Zertifikat wird im zentralen Verwaltungsspeicher für alle anderen Server gespeichert.
  
Zusätzliche Informationen werden benötigt, um die Optionen und Anforderungen bei der Verwendung des Set-CsCertificate-Cmdlet zum Bereitstellen von Zertifikaten vor dem Ablauf des aktuellen Zertifikats nachvollziehen zu können. Der Parameter "-Roll" ist wichtig, aber im Wesentlichen ein einzelner Zweck. Wenn Sie ihn als Parameter definieren, teilen Sie Set-CsCertificate mit, dass Sie Informationen über das Zertifikat bereitstellen, das durch "-Type" (z. B. "AudioVideoAuthentication" und "OAuthTokenIssuer") betroffen ist, wenn das Zertifikat durch "-EffectiveDate" definiert wird.
  
 **-Roll**: Der Parameter "-Roll" ist erforderlich und weist Abhängigkeiten auf, die mit ihm angegeben werden müssen. Parameter, die zum Festlegen der betroffenen Zertifikate und ihrer Anwendungsweise erforderlich sind:
  
 **-EffectiveDate**: Der Parameter -EffectiveDate definiert, wann das neue Zertifikat mit dem aktuellen Zertifikat koaktiv wird. Das -EffectiveDate kann sich in der Nähe des Ablaufdatums des aktuellen Zertifikats befinden, oder es kann einen längeren Zeitraum sein. Ein empfohlenes Minimum für "-EffectiveDate" für das AudioVideoAuthentication-Zertifikat beträgt 8 Stunden. Dies ist die Standardtokenlebensdauer für AV-Edgediensttoken, die mithilfe des AudioVideoAuthentication-Zertifikats ausgestellt wurden.
  
Für das Bereitstellen der OAuthTokenIssuer-Zertifikate liegen verschiedene Anforderungen für die Durchlaufzeit vor, bevor das Zertifikat wirksam werden kann. Der Mindestwert des OAuthTokenIssuer-Zertifikats für die Durchlaufzeit sollte 24 Stunden vor der Ablaufzeit des aktuellen Zertifikats betragen. Die erweiterte Durchlaufzeit für die Koexistenz ist durch andere Serverrollen begründet, die von dem OAuthTokenIssuer-Zertifikat (beispielsweise Exchange Server) abhängen, das eine längere Aufbewahrungszeit für durch Zertifikate erstellte Authentifizierungs- und Verschlüsselungsschlüsselelemente besitzt.
  
 **-Thumbprint**: Beim Fingerabdruck handelt es sich um ein für dieses Zertifikat eindeutiges Attribut. Der Parameter "-Thumbprint" wird verwendet, um das Zertifikat zu identifizieren, das von den Aktionen des Cmdlets Set-CsCertificate betroffen ist.
  
 **-Type**: Der Parameter "-Type" kann einen einzelnen Zertifikatverwendungstyp oder eine durch Kommas getrennte Liste der Zertifikatverwendungstypen akzeptieren. Die Zertifikattypen geben für das Cmdlet und den Server an, worin der Zweck des Zertifikats besteht. Der Typ "AudioVideoAuthentication" ist beispielsweise für die Verwendung durch den A/V-Edgedienst und den AV-Authentifizierungsdienst vorgesehen. Wenn Sie verschiedene Zertifikattypen zum gleichen Zeitpunkt bereitstellen möchten, müssen Sie die längste effektive Mindestdurchlaufzeit für die Zertifikate berücksichtigen. Sie müssen beispielsweise Zertifikate vom Typ "AudioVideoAuthentication" und Typ "OAuthTokenIssuer" bereitstellen. Ihr Minimum -EffectiveDate muss der größere der beiden Zertifikate sein, in diesem Fall OAuthTokenIssuer, der eine mindeste Vorlaufzeit von 24 Stunden hat. Wenn Sie das Zertifikat "AudioVideoAuthentication" nicht mit einer Durchlaufzeit von 24 Stunden bereitstellen möchten, stellen Sie es separat mit einem Ihren Anforderungen entsprechenden Wert für "EffectiveDate" bereit.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein A/V-Edgedienstzertifikat mit den Parametern "-Roll" und "-EffectiveDate"

1. Melden Sie sich beim lokalen Computer als Mitglied der Gruppe "Administratoren" an.
    
2. Fordern Sie eine Verlängerung oder ein neues AudioVideoAuthentication-Zertifikat mit exportierbarem privaten Schlüssel für das vorhandene Zertifikat im A/V-Edgedienst an.
    
3. Importieren Sie das neue AudioVideoAuthentication-Zertifikat auf den Edgeserver und alle anderen Edgeserver in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben).
    
4. Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet Set-CsCertificate, und verwenden Sie den Parameter "-Roll" mit dem Parameter "-EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden. Dadurch erhalten wir eine Zeit, in der das Zertifikat auf "aktiv" festgelegt werden muss, und ist das -EffectiveDate \<string\> : "22.07.2015 06:00:00 Uhr". 
    
    > [!IMPORTANT]
    > Für einen Edgepool müssen alle AudioVideoAuthentication-Zertifikate bereitgestellt und nach dem Datum und der Uhrzeit bereitgestellt werden, die durch den Parameter "-EffectiveDate" des ersten bereitgestellten Zertifikats definiert sind, um mögliche Unterbrechungen der A/V-Kommunikation aufgrund des ablaufenden älteren Zertifikats zu vermeiden, bevor alle Client- und Consumertoken mithilfe des neuen Zertifikats erneuert wurden. 
  
    Der Befehl Set-CsCertificate mit dem Parameter "-Roll" und "-EffectiveTime":
    
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
    > Das EffectiveDate muss so formatiert sein, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet. 
  
Um den Prozess weiter zu verstehen, den Set-CsCertificate, -Roll und -EffectiveDate zum Bereitstellen eines neuen Zertifikats zum Ausstellen neuer AudioVideoAuthentication-Token verwendet, während weiterhin ein vorhandenes Zertifikat zum Überprüfen von AudioVideoAuthentication verwendet wird, die von Consumern verwendet werden, ist eine visuelle Zeitachse ein effektives Mittel zum Verständnis des Prozesses. Im folgenden Beispiel ermittelt der Administrator, dass das A/V-Edgedienstzertifikat am 22.07.2015 um 14:00:00 Uhr abläuft. Er fordert ein neues Zertifikat an und erhält es und importiert es auf jeden Edgeserver in seinem Pool. Am 22.07.2015 um 02:00 Uhr beginnt er mit der Ausführung Get-CsCertificate mit -Roll, -Thumbprint, der der Fingerabdruckzeichenfolge des neuen Zertifikats entspricht, und -EffectiveTime, festgelegt auf 22.07.2015 06:00:00 Uhr. Er führt diesen Befehl auf jedem Edgeserver aus.
  
![Verwenden der Parameter "Roll" und "EffectiveDate".](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Stufe**|
|:-----|:-----|
|1  <br/> |Start: 22.07.2015 12:00:00 Uhr  <br/> Das aktuelle AudioVideoAuthentication-Zertifikat läuft am 22.07.2015 um 14:00 Uhr ab. Dies wird durch den Ablaufzeitstempel auf dem Zertifikat bestimmt. Planen Sie den Austausch und die Rollover Ihres Zertifikats so, dass eine 8-Stunden-Überlappung (Standardtokenlebensdauer) berücksichtigt wird, bevor das vorhandene Zertifikat die Ablaufzeit erreicht. Die Vorlaufzeit von 2:00:00 Uhr wird in diesem Beispiel verwendet, damit der Administrator genügend Zeit zum Platzieren und Bereitstellen der neuen Zertifikate vor der Effektivzeit von 6:00:00 Uhr hat.  <br/> |
|2  <br/> |22.07.2015 02:00:00 - 22.07.2015 5:59:59 Uhr  <br/> Festlegen von Zertifikaten auf Edgeservern mit einer Effektivzeit von 6:00:00 Uhr (4-Stunden-Vorlaufzeit ist für dieses Beispiel, kann jedoch länger sein) mit Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate \<datetime string of the effective time for new certificate\>  <br/> |
|3  <br/> |22.07.2015 06:00 - 22.07.2015 14:00 Uhr  <br/> Zum Überprüfen von Token wird zuerst das neue Zertifikat ausprobiert, und wenn das neue Zertifikat das Token nicht überprüft, wird das alte Zertifikat ausprobiert. Dieser Prozess wird für alle Token während des 8-Stunden-Überlappungszeitraums (Standardtokenlebensdauer) verwendet.  <br/> |
|4  <br/> |Ende: 22.07.2015 14:00:01 Uhr  <br/> Das alte Zertifikat ist abgelaufen, und das neue Zertifikat wurde übernommen. Altes Zertifikat kann mit Remove-CsCertificate -Type -Previous sicher entfernt werden \<certificate usage type\>  <br/> |
   
Wenn der Gültigkeitszeitpunkt erreicht ist (22.07.2015 06:00:00 Uhr), werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2015, 14:00:00 Uhr), werden Token nur vom neuen Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets Remove-CsCertificate mit dem Parameter "-Previous" sicher entfernt werden.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein OAuthTokenIssuer-Zertifikat mit den Parametern "-Roll" und "-EffectiveDate"

1. Melden Sie sich beim lokalen Computer als Mitglied der Gruppe "Administratoren" an.
    
2. Fordern Sie eine Verlängerung oder ein neues OAuthTokenIssuer-Zertifikat mit exportierbarem privaten Schlüssel für das vorhandene Zertifikat auf dem Front-End-Server an.
    
3. Importieren Sie das neue OAuthTokenIssuer-Zertifikat auf einen Front-End-Server in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben). Das OAuthTokenIssuer-Zertifikat wird global repliziert und muss auf den Servern in Ihrer Bereitstellung aktualisiert und erneuert werden. Als Beispiel wird der Front-End-Server verwendet.
    
4. Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet Set-CsCertificate, und verwenden Sie den Parameter "-Roll" mit dem Parameter "-EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden. 
    
    Der Befehl Set-CsCertificate mit dem Parameter "-Roll" und "-EffectiveTime":
    
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
> Das EffectiveDate muss so formatiert sein, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet. 
  
Wenn der Gültigkeitszeitpunkt erreicht ist (21.07.2015 1:00:00 Uhr), werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2015, 14:00:00 Uhr), werden Token nur vom neuen Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets Remove-CsCertificate mit dem Parameter "-Previous" sicher entfernt werden.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Siehe auch

[Verwalten der Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate?view=skype-ps)