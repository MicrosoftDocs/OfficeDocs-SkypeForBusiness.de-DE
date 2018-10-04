---
title: Bereitstellen von AV- und OAuth-Zertifikaten in Skype für Business Server mithilfe von-Roll in Set-CsCertificate
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Zusammenfassung: Phase AV- und OAuth Zertifikate für Skype für Business Server.'
ms.openlocfilehash: 9fd4074034e9bff6b27ed9a22143c59dc9890821
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375936"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Bereitstellen von AV- und OAuth-Zertifikaten in Skype für Business Server mithilfe von-Roll in Set-CsCertificate
 
**Zusammenfassung:** Phase AV- und OAuth-Zertifikaten für Skype für Business Server.
  
Audio/Video (A / V) Communications ist eine wichtige Komponente von Skype für Business Server. Features wie etwa Anwendung freigeben und Audio- und Videokonferenzen beruhen auf die Zertifikate zugewiesen sind, der a / V-edgedienst, insbesondere der A / V-Authentifizierungsdienst.
  
> [!IMPORTANT]
> Dieses neue Feature wurde entwickelt für den A / V-edgedienst und OAuthTokenIssuer-Zertifikat. Andere Zertifikattypen bereitgestellt werden können, zusammen mit dem A / V-edgedienst und OAuth-Zertifikats Typ, aber haben keinen Nutzen aus der Koexistenzverhalten, A / V-Edgeserver das Zertifikat wird.
  
Die Skype für Business Server Management Shell PowerShell-Cmdlets zur Verwaltung von Skype für Business Serverzertifikate bezieht sich auf den A / V-edgedienst Zertifikat als Typ AudioVideoAuthentication-Zertifikat und das OAuthServer als TypeOAuthTokenIssuer. Für den Rest dieses Themas und um die Zertifikate eindeutig zu identifizieren werden sie durch den Bezeichnertyp AudioVideoAuthentication AndOAuthTokenIssuer bezeichnet werden.
  
Der A / V-Authentifizierungsdienst ist dafür verantwortlich, Ausstellen von Token, die von Clients und anderen A verwendet werden / V-Consumer. Die Token aus Attribute für das Zertifikat generiert und bei Ablauf des Zertifikats ergeben Verlust der Verbindung und die Anforderung an einen neuen Token generiert, die für das neue Zertifikat erneut an. Ein neues Feature in Skype für Business Server wird dieses Problem - die Möglichkeit, ein neues Zertifikat, bevor der alte Datenbankserver ablaufen und ermöglichen beide Zertifikate für eine bestimmte Zeitspanne funktionieren weiterhin Phase verringern. Diese Funktion nutzt aktualisierte Funktionalität in der Set-CsCertificate Skype für Business Server-Verwaltungsshell-Cmdlet. Der neue Parameter-Würfeln, mit dem vorhandenen Parameter - EffectiveDate, das neue AudioVideoAuthentication-Zertifikat im Zertifikatspeicher platziert wird. Das ältere AudioVideoAuthentication-Zertifikat bleibt weiterhin für ausgestellten Token anhand überprüft werden. Bereitstellen des neuen AudioVideoAuthentication-Zertifikats ab, wird die folgende Reihe von Ereignissen auftreten:
  
> [!TIP]
> Verwenden die Skype als Business Server-Verwaltungsshell-Cmdlets zum Verwalten von Zertifikaten, können Sie für jeden Zweck auf dem Edgeserver separate und eigenständige Zertifikate anfordern. Mit den Zertifikat-Assistenten in der Skype für Business Server Installations-Assistent hilft Ihnen beim Erstellen von Zertifikaten, aber in der Regel **dem Standardtyp welche Paare alle Zertifikat für den Edgeserver in einem einzigen Zertifikat verwendet** wird. Die empfohlene Vorgehensweise bei Verwendung der Funktion für rollende Zertifikate besteht darin, das AudioVideoAuthentication-Zertifikat von den anderen Zertifikatzwecken zu lösen. Sie können ein Zertifikat vom Typ „Standard“ bereitstellen, doch nur der AudioVideoAuthentication-Teil des kombinierten Zertifikats profitiert von dem Staging. Ein Benutzer beteiligt (z. b) eine Sofortnachrichtenunterhaltung, wenn das Zertifikat abläuft ab-und wieder anmelden, um zu machen müssen mithilfe des neuen Zertifikats mit Zugriffs-edgedienst verknüpft ist. Ähnliches Verhalten tritt für einen Benutzer einer Webkonferenz mithilfe des Webkonferenz-edgediensts beteiligt. Das OAuthTokenIssuer-Zertifikat ist ein bestimmter Typ, der auf allen Servern freigegeben ist. Sie erstellen und Verwalten des Zertifikats an einem Ort und das Zertifikat wird gespeichert im zentralen Verwaltungsspeicher für alle anderen Server.
  
Zusätzliche Informationen werden benötigt, um die Optionen und Anforderungen bei der Verwendung des Set-CsCertificate-Cmdlets zum Bereitstellen von Zertifikaten vor dem Ablauf des aktuellen Zertifikats nachvollziehen zu können. Die - Roll Parameter ist wichtig, aber einzelne im wesentlichen Zweck. Wenn Sie als Parameter definieren, werden Sie Set-CsCertificate, die Sie bereitstellen werden werden Informationen über das Zertifikat betroffen sein von - definierten mitteilen Typs (beispielsweise AudioVideoAuthentication und OAuthTokenIssuer), wenn das Zertifikat wird die Übermittlung wirksamer durch - EffectiveDate definiert.
  
 **-Ein Rollback**:-Roll Parameter ist erforderlich und hat Abhängigkeiten, die zusammen mit dem angegeben werden müssen. Parameter, die zum Festlegen der betroffenen Zertifikate und ihrer Anwendungsweise erforderlich sind:
  
 **EffectiveDate-**: der Parameter - EffectiveDate definiert, wann das neue Zertifikat mit dem aktuellen Zertifikat co-active gestellt wird. EffectiveDate - kann ungefähr die Ablaufzeit für das aktuelle Zertifikat, oder es kann sich um einen längeren Zeitraum. Eine empfohlene minimale - EffectiveDate für das AudioVideoAuthentication-Zertifikat wäre 8 Stunden, also die standardmäßige Gültigkeitsdauer von token für a/v-Edgeserver Service Token mit AudioVideoAuthentication-Zertifikat ausgestellt.
  
Für das Bereitstellen der OAuthTokenIssuer-Zertifikate liegen verschiedene Anforderungen für die Vorlaufzeit vor, bevor das Zertifikat wirksam werden kann. Der Mindestwert des OAuthTokenIssuer-Zertifikats für die Vorlaufzeit sollte 24 Stunden vor der Ablaufzeit des aktuellen Zertifikats betragen. Die erweiterte Vorlaufzeit für die Koexistenz ist durch andere Serverrollen begründet, die von dem OAuthTokenIssuer-Zertifikat (beispielsweise Exchange Server) abhängen, das eine längere Aufbewahrungszeit für durch Zertifikate erstellte Authentifizierungs- und Verschlüsselungsschlüsselelemente besitzt.
  
 **-Thumbprint**: Beim Fingerabdruck handelt es sich um ein für dieses Zertifikat eindeutiges Attribut. Den Fingerabdruck des - Parameter verwendet wird, um das Zertifikat zu identifizieren, die betroffen sein durch die Aktionen des Cmdlets Set-CsCertificate.
  
 **-Typ**:-Type-Parameter kann ein einzelnes Zertifikat Verwendungstyp oder eine durch Kommas getrennte Liste mit Verwendungstypen Zertifikat akzeptieren. Die Zertifikattypen geben für das Cmdlet und den Server an, worin der Zweck des Zertifikats besteht. Typ AudioVideoAuthentication ist beispielsweise für die Verwendung durch den A / V-edgedienst und a/v-Authentifizierungsdienst. Wenn Sie verschiedene Zertifikattypen zum gleichen Zeitpunkt bereitstellen möchten, müssen Sie die längste effektive Mindestvorlaufzeit für die Zertifikate berücksichtigen. Sie müssen beispielsweise Zertifikate vom Typ „AudioVideoAuthentication“ und vom Typ „OAuthTokenIssuer“ bereitstellen. Die minimale - EffectiveDate muss die zwei Zertifikate, in diesem Fall die OAuthTokenIssuer größer sein, die eine minimale Zeitabstand von 24 Stunden hat. Wenn Sie das Zertifikat „AudioVideoAuthentication“ nicht mit einer Vorlaufzeit von 24 Stunden bereitstellen möchten, stellen Sie es separat mit einem Ihren Anforderungen entsprechenden Wert für „EffectiveDate“ bereit.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>So aktualisieren oder Erneuern eines A / V-edgedienst Zertifikat mit einem - Roll "und" - EffectiveDate-Parameter

1. Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.
    
2. Fordern Sie eine Erneuerung oder ein neues AudioVideoAuthentication-Zertifikat mit exportierbarem privatem Schlüssel für das vorhandene Zertifikat für den A / V-edgedienst.
    
3. Importieren Sie das neue AudioVideoAuthentication-Zertifikat auf dem Edge-Server und alle anderen Edge-Server in Ihrem Pool (Wenn Sie einen Pool bereitgestellt haben).
    
4. Das importierte Zertifikat mit dem Cmdlet Set-CsCertificate konfigurieren und Verwenden der - Roll-Parameter mit dem EffectiveDate - Parameter. Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokenlebensdauer (standardmäßig acht Stunden) festgelegt werden. Dies liefert uns eine Zeit, die das Zertifikat auf aktiv eingestellt werden muss, und ist - EffectiveDate \<Zeichenfolge\>: "7/22/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Für einen Edge-Pools müssen alle AudioVideoAuthentication Zertifikate bereitgestellt und von Datum und Uhrzeit definiert durch den Parameter "- EffectiveDate" des ersten Zertifikats bereitgestellt, um eine mögliche vermeiden bereitgestellt / V Communications Unterbrechung aufgrund der älteren das Zertifikat abläuft, bevor alle Client- und Consumer Token mithilfe des neuen Zertifikats erneuert wurden. 
  
    Mit dem Parameter Roll "und" – EffectiveTime Befehl "Set-CsCertificate":
    
   ```
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Ein Set-CsCertificate-Beispielbefehl:
    
   ```
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > Die EffectiveDate muss entsprechend Ihrer Server Region und spracheinstellungen formatiert werden. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet. 
  
Um dem Vorgang zu veranschaulichen, Set-CsCertificate - Roll und -EffectiveDate verwenden, um die Stufe eines neuen Zertifikats für die neue AudioVideoAuthentication-Token gleichzeitiger Verwendung eines vorhandenen Zertifikats AudioVideoAuthentication überprüft, die verwendet werden Consumer ist eine visual Zeitachse ein effektives Mittel zum Verständnis des Prozess. Im folgenden Beispiel der Administrator bestimmt, die dem A / V-Edgeserver das Zertifikat ist fällig bis zu 2:00:00 Uhr am 07/22/2015 ablaufen. Er fordert und erhält ein neues Zertifikat und dann in seinem Pool in jedem Edgeserver importiert. Um 2 Uhr am 07/22/2015, er beginnt mit Get-CsCertificate - Roll, - Fingerabdruck gleich der Zeichenfolge Fingerabdruck des neuen Zertifikats und -EffectiveTime auf 07/22/2015 festgelegt werden 6:00:00 Uhr. Er führt diesen Befehl auf jedem Edgeserver.
  
![Verwenden der Parameter "Roll" und "EffectiveDate"](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Beschriftung**|**Phase**|
|:-----|:-----|
|1  <br/> |Start: 22.07.2015 12:00:00 Uhr  <br/> Das aktuelle AudioVideoAuthentication-Zertifikat endet am 22.07.2015 um 14:00 Uhr. Das wird durch den Ablaufzeitstempel auf dem Zertifikat festgelegt. Planen Sie für Ersatz und Rollover Ihres Zertifikats eine Überschneidung von acht Stunden ein (Standardtokenlebensdauer), bevor das vorhandene Zertifikat die Ablaufzeit erreicht. Die Vorlaufzeit von 2:00:00 Uhr wird in diesem Beispiel verwendet, damit der Administrator genügend Zeit hat, um die neuen Zertifikate vor der Ablaufzeit um 6:00:00 Uhr zu platzieren und bereitzustellen.  <br/> |
|2  <br/> |22.07.2015 02:00:00 Uhr – 22.07.2015 05:59:59 Uhr  <br/> Legen Sie Zertifikate auf Edge-Servern mit effektiven Zeit von 6:00:00 AM (4 Stunden Zeitabstand für dieses Beispiel ist, jedoch kann nicht länger) mithilfe des Set-CsCertificate-Typ \<Zertifikat Verwendungstyp\> -Fingerabdruck \<Fingerabdruck des neuen Zertifikats\> - Ein Rollback - EffectiveDate \<Datetime-Zeichenfolge der effektiven Zeit für das neue Zertifikat\>  <br/> |
|3  <br/> |22.07.2015 06:00 Uhr – 22.07.2015 14:00 Uhr  <br/> Zur Überprüfung von Token wird zunächst das neue Zertifikat ausprobiert und wenn das neue Zertifikat das Token nicht validieren kann, wird das alte Zertifikat verwendet. Dieser Prozess wird während der Überscheidungszeit von 8 Stunden (Standardtokenlebensdauer) für alle Token verwendet.  <br/> |
|4  <br/> |Ende: 22.07.2015 14:00:01 Uhr  <br/> Das alte Zertifikat ist abgelaufen und das neue Zertifikat ist nun in Kraft. Alte Zertifikat kann sicher entfernt werden mit Remove-CsCertificate-Typ \<Zertifikat Verwendungstyp\> -vorherigen  <br/> |
   
Wird das Gültigkeitsdatum (22.07.2015 06:00:00 Uhr) erreicht, werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2015 14:00:00 Uhr), werden Token nur durch das neue Zertifikat überprüft. Das alte Zertifikat kann sicher mit dem Remove-CsCertificate-Cmdlet entfernt werden mit dem vorherigen Parameter.

```
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>So aktualisieren oder Erneuen Sie ein OAuthTokenIssuer Zertifikat mit einem - Roll "und" - EffectiveDate-Parameter

1. Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.
    
2. Fordern Sie eine Erneuerung oder ein neues OAuthTokenIssuer-Zertifikat mit exportierbarem privatem Schlüssel für das vorhandene Zertifikat für den Front-End-Server.
    
3. Importieren Sie das neue OAuthTokenIssuer-Zertifikat auf einem Front-End-Server in Ihrem Pool (Wenn Sie einen Pool bereitgestellt haben). Das OAuthTokenIssuer-Zertifikat wird global repliziert und muss auf den Servern in Ihrer Bereitstellung aktualisiert und erneuert werden. Der Front-End-Server wird als Beispiel verwendet.
    
4. Das importierte Zertifikat mit dem Cmdlet Set-CsCertificate konfigurieren und Verwenden der - Roll-Parameter mit dem EffectiveDate - Parameter. Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus mindestens 24 Stunden festgelegt werden. 
    
    Mit dem Parameter Roll "und" – EffectiveTime Befehl "Set-CsCertificate":
    
   ```
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Ein Set-CsCertificate-Beispielbefehl:
    
  ```
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> Die EffectiveDate muss entsprechend Ihrer Server Region und spracheinstellungen formatiert werden. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet. 
  
Wird das Gültigkeitsdatum (21.07.2015 01:00:00 Uhr) erreicht, werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2015 14:00:00 Uhr), werden Token nur durch das neue Zertifikat überprüft. Das alte Zertifikat kann sicher mit dem Remove-CsCertificate-Cmdlet entfernt werden mit dem vorherigen Parameter.
```
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Server-zu-Server-Authentifizierung (OAuth) und partneranwendungen in Skype für Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)