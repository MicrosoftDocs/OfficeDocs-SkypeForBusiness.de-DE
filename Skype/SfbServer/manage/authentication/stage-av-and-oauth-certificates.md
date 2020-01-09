---
title: Stage AV-und OAuth-Zertifikate in Skype for Business Server Using-Rolle in Satz-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Zusammenfassung: Stage AV-und OAuth-Zertifikate für Skype for Business Server.'
ms.openlocfilehash: 37edb6843d420ca3387958c54b3db8c72a28be92
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991960"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Stage AV-und OAuth-Zertifikate in Skype for Business Server Using-Rolle in Satz-CsCertificate
 
**Zusammenfassung:** Stage AV-und OAuth-Zertifikate für Skype for Business Server.
  
Audio/Video (a/V)-Kommunikation ist eine wichtige Komponente von Skype for Business Server. Features wie Anwendungsfreigabe und Audio-und Videokonferenzen basieren auf den Zertifikaten, die dem a/v-Edgedienst, insbesondere dem a/v-Authentifizierungsdienst, zugewiesen sind.
  
> [!IMPORTANT]
> Dieses neue Feature ist für den A/V-Edgedienst und das OAuthTokenIssuer-Zertifikat konzipiert. Andere Zertifikattypen können zusammen mit dem a/v-Edgedienst und dem OAuth-Zertifikattyp bereitgestellt werden, profitieren aber nicht vom Koexistenzsystem, das vom a/v-Edgedienst-Zertifikat bereitgestellt wird.
  
Die für die Verwaltung von Skype for Business Server-Zertifikaten verwendeten PowerShell-Cmdlets für Skype for Business Server-Verwaltungsshell bezieht sich auf das A/V-Edgedienst Zertifikat als AudioVideoAuthentication-Zertifikattyp und das OAuthServer-Zertifikat als typeOAuthTokenIssuer. Im weiteren Verlauf dieses Themas und zum eindeutigen Identifizieren der Zertifikate werden Sie mit dem gleichen Identifier-Typ, AudioVideoAuthentication andOAuthTokenIssuer, bezeichnet.
  
Der a/v-Authentifizierungsdienst ist für das Ausgeben von Token verantwortlich, die von Clients und anderen a/v-Consumern verwendet werden. Die Token werden aus Attributen auf dem Zertifikat generiert, und wenn das Zertifikat abläuft, führt dies zu einem Verbindungsabbruch und einer Anforderung, erneut mit einem neuen Token zu verbinden, das vom neuen Zertifikat generiert wird. Ein neues Feature in Skype for Business Server wird dieses Problem lindern – die Möglichkeit, ein neues Zertifikat im Vorfeld des alten zu inszenieren, das abläuft und es ermöglicht, dass beide Zertifikate während eines bestimmten Zeitraums weiterhin funktionieren. Dieses Feature verwendet aktualisierte Funktionen im Cmdlet "Satz-CsCertificate" von Skype for Business Server-Verwaltungsshell. Mit dem neuen Parameter-Rolle mit dem vorhandenen Parameter-EffectiveDate wird das neue AudioVideoAuthentication-Zertifikat im Zertifikatspeicher platziert. Das ältere AudioVideoAuthentication-Zertifikat bleibt für ausgestellte Token weiterhin gültig. Beginnend mit dem Setzen des neuen AudioVideoAuthentication-Zertifikats wird die folgende Reihe von Ereignissen auftreten:
  
> [!TIP]
> Mit den Skype for Business Server-Verwaltungsshell-Cmdlets für die Verwaltung von Zertifikaten können Sie für jeden Zweck auf dem Edgeserver getrennte und unterschiedliche Zertifikate anfordern. Die Verwendung des Zertifikat-Assistenten im Bereitstellungs-Assistenten von Skype for Business Server unterstützt Sie beim Erstellen von Zertifikaten, ist in der Regel aber der **Standardtyp** , mit dem alle Zertifikat Verwendungen für den Edgeserver auf einem einzigen Zertifikat kombiniert werden. Die empfohlene Vorgehensweise bei Verwendung der Funktion für rollende Zertifikate besteht darin, das AudioVideoAuthentication-Zertifikat von den anderen Zertifikatzwecken zu lösen. Sie können ein Zertifikat vom Typ „Standard“ bereitstellen, doch nur der AudioVideoAuthentication-Teil des kombinierten Zertifikats profitiert von dem Staging. Ein Benutzer, der an (beispielsweise) einer Sofortnachrichtenunterhaltung teilhat, wenn das Zertifikat abläuft, muss sich abmelden und wieder anmelden, um das neue Zertifikat zu verwenden, das dem Access Edge-Dienst zugeordnet ist. Ein ähnliches Verhalten tritt für einen Benutzer ein, der mit dem Webkonferenz-Edgedienst an einer Webkonferenz teilnimmt. Das OAuthTokenIssuer-Zertifikat ist ein bestimmter Typ, der auf allen Servern freigegeben ist. Sie erstellen und verwalten das Zertifikat an einer zentralen Stelle, und das Zertifikat wird im zentralen Verwaltungsspeicher für alle anderen Server gespeichert.
  
Zusätzliche Informationen werden benötigt, um die Optionen und Anforderungen bei der Verwendung des Set-CsCertificate-Cmdlets zum Bereitstellen von Zertifikaten vor dem Ablauf des aktuellen Zertifikats nachvollziehen zu können. Der-Rolle-Parameter ist wichtig, aber im Wesentlichen ein einziger Zweck. Wenn Sie es als Parameter definieren, geben Sie "CsCertificate" an, dass Sie Informationen zu dem Zertifikat bereitstellen werden, das von Typ (beispielsweise AudioVideoAuthentication und OAuthTokenIssuer) betroffen sein wird, wenn das Zertifikat effektiv definiert von-EffectiveDate.
  
 **-Rolle**: der-Rolle-Parameter ist erforderlich und weist Abhängigkeiten auf, die zusammen mit ihm bereitgestellt werden müssen. Parameter, die zum Festlegen der betroffenen Zertifikate und ihrer Anwendungsweise erforderlich sind:
  
 **-EffectiveDate**: der Parameter-EffectiveDate definiert, wann das neue Zertifikat mit dem aktuellen Zertifikat gemeinsam aktiv wird. Das-EffectiveDate kann in der Nähe der Ablaufzeit des aktuellen Zertifikats liegen, oder es kann einen längeren Zeitraum dauern. Ein Empfohlenes Mindest-EffectiveDate für das AudioVideoAuthentication-Zertifikat wäre 8 Stunden, was die standardmäßige Token-Lebensdauer für AV-Edgedienst-Token ist, die mit dem AudioVideoAuthentication-Zertifikat ausgegeben werden.
  
Für das Bereitstellen der OAuthTokenIssuer-Zertifikate liegen verschiedene Anforderungen für die Vorlaufzeit vor, bevor das Zertifikat wirksam werden kann. Der Mindestwert des OAuthTokenIssuer-Zertifikats für die Vorlaufzeit sollte 24 Stunden vor der Ablaufzeit des aktuellen Zertifikats betragen. Die erweiterte Vorlaufzeit für die Koexistenz ist durch andere Serverrollen begründet, die von dem OAuthTokenIssuer-Zertifikat (beispielsweise Exchange Server) abhängen, das eine längere Aufbewahrungszeit für durch Zertifikate erstellte Authentifizierungs- und Verschlüsselungsschlüsselelemente besitzt.
  
 **-Thumbprint**: Beim Fingerabdruck handelt es sich um ein für dieses Zertifikat eindeutiges Attribut. Der-Fingerabdruck-Parameter wird verwendet, um das Zertifikat zu identifizieren, das von den Aktionen des Cmdlets "CsCertificate" betroffen ist.
  
 **-Type**: der-Type-Parameter kann einen einzelnen Zertifikat Nutzungstyp oder eine durch trennzeichengetrennte Liste der Zertifikat Verwendungstypen akzeptieren. Die Zertifikattypen geben für das Cmdlet und den Server an, worin der Zweck des Zertifikats besteht. Geben Sie beispielsweise AudioVideoAuthentication ein, um den A/V-Edgedienst und den AV-Authentifizierungsdienst zu verwenden. Wenn Sie verschiedene Zertifikattypen zum gleichen Zeitpunkt bereitstellen möchten, müssen Sie die längste effektive Mindestvorlaufzeit für die Zertifikate berücksichtigen. Sie müssen beispielsweise Zertifikate vom Typ „AudioVideoAuthentication“ und vom Typ „OAuthTokenIssuer“ bereitstellen. Ihre Mindest-EffectiveDate muss das größere der beiden Zertifikate sein, in diesem Fall die OAuthTokenIssuer, die eine minimale Durchlaufzeit von 24 Stunden hat. Wenn Sie das Zertifikat „AudioVideoAuthentication“ nicht mit einer Vorlaufzeit von 24 Stunden bereitstellen möchten, stellen Sie es separat mit einem Ihren Anforderungen entsprechenden Wert für „EffectiveDate“ bereit.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein a/V-Edgedienst-Zertifikat mit einem-Rollen-und-EffectiveDate-Parameter

1. Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.
    
2. Fordern Sie ein Erneuerungs-oder neues AudioVideoAuthentication-Zertifikat mit exportier barem privaten Schlüssel für das vorhandene Zertifikat im a/V-Edgedienst an.
    
3. Importieren Sie das neue AudioVideoAuthentication-Zertifikat auf den Edgeserver und alle anderen Edgeserver in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben).
    
4. Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet "Satz-CsCertificate", und verwenden Sie den Parameter "-Rolle" mit dem Parameter-EffectiveDate. Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokenlebensdauer (standardmäßig acht Stunden) festgelegt werden. Dadurch erhalten wir eine Uhrzeit, zu der das Zertifikat auf "aktiv" festgesetzt werden muss, \<und\>ist die-EffectiveDate-Zeichenfolge: "7/22/2015 6:00:00 am". 
    
    > [!IMPORTANT]
    > Bei einem Edge-Pool müssen alle AudioVideoAuthentication-Zertifikate bereitgestellt und durch das Datum und die Uhrzeit bereitgestellt werden, die durch den-EffectiveDate-Parameter des ersten bereitgestellten Zertifikats definiert wurden, um mögliche A/V-KOMMUNIKATIONSUNTERBRECHUNGEN zu vermeiden, weil das ältere Zertifikat abläuft, bevor alle Client-und Consumer-Token mit dem neuen Zertifikat erneuert wurden. 
  
    Der Befehl "Satz-CsCertificate" mit dem Parameter "-Rolle" und "-effektiv":
    
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
    > Die EffectiveDate muss so formatiert sein, dass Sie den Regions-und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet. 
  
So verstehen Sie den Prozess, der von CsCertificate,-Rolle und-EffectiveDate verwendet wird, um ein neues Zertifikat zur Ausgabe neuer AudioVideoAuthentication-Token zu inszenieren, während weiterhin ein vorhandenes Zertifikat zur Überprüfung von AudioVideoAuthentication verwendet wird von Verbrauchern ist eine visuelle Zeitachse ein wirksames Mittel, um den Prozess zu verstehen. Im folgenden Beispiel wird vom Administrator festgelegt, dass das A/V-Edgedienst-Zertifikat um 2:00:00 Uhr am 07/22/2015 abläuft. Er fordert und empfängt ein neues Zertifikat und importiert es auf jeden Edgeserver in seinem Pool. Um 2 Uhr auf 07/22/2015 beginnt er mit der Ausführung von Get-CsCertificate mit-Rolle,-Fingerabdruck, der der Fingerabdruck Zeichenfolge des neuen Zertifikats entspricht, und-Effektivzeit, die auf 07/22/2015 6:00:00 Uhr eingestellt ist. Er führt diesen Befehl auf jedem Edgeserver aus.
  
![Verwenden des Rollen-und des EffectiveDate-Parameters](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Beschriftung**|**Phase**|
|:-----|:-----|
|1  <br/> |Start: 22.07.2015 12:00:00 Uhr  <br/> Das aktuelle AudioVideoAuthentication-Zertifikat endet am 22.07.2015 um 14:00 Uhr. Das wird durch den Ablaufzeitstempel auf dem Zertifikat festgelegt. Planen Sie für Ersatz und Rollover Ihres Zertifikats eine Überschneidung von acht Stunden ein (Standardtokenlebensdauer), bevor das vorhandene Zertifikat die Ablaufzeit erreicht. Die Vorlaufzeit von 2:00:00 Uhr wird in diesem Beispiel verwendet, damit der Administrator genügend Zeit hat, um die neuen Zertifikate vor der Ablaufzeit um 6:00:00 Uhr zu platzieren und bereitzustellen.  <br/> |
|2  <br/> |22.07.2015 02:00:00 Uhr – 22.07.2015 05:59:59 Uhr  <br/> Sie können Zertifikate auf Edgeserver mit einer effektiven Zeitspanne von 6:00:00 am (4 Stunden Vorlaufzeit für dieses Beispiel, aber länger) verwenden, indem Sie \<die CsCertificate-\> Art des \<Zertifikat Verwendungs Typs-\> Fingerabdruck des neuen \<Zertifikats-Rollen-EffectiveDate DateTime-Zeichenfolge der Gültigkeitsdauer für neues Zertifikat\>  <br/> |
|3  <br/> |22.07.2015 06:00 Uhr – 22.07.2015 14:00 Uhr  <br/> Zur Überprüfung von Token wird zunächst das neue Zertifikat ausprobiert und wenn das neue Zertifikat das Token nicht validieren kann, wird das alte Zertifikat verwendet. Dieser Prozess wird während der Überscheidungszeit von 8 Stunden (Standardtokenlebensdauer) für alle Token verwendet.  <br/> |
|4  <br/> |Ende: 22.07.2015 14:00:01 Uhr  <br/> Das alte Zertifikat ist abgelaufen und das neue Zertifikat ist nun in Kraft. Altes Zertifikat kann sicher mit Remove-CsCertificate-Type \<Certificate Usage Type\> -Previous entfernt werden  <br/> |
   
Wird das Gültigkeitsdatum (22.07.2015 06:00:00 Uhr) erreicht, werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2015 14:00:00 Uhr), werden Token nur durch das neue Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets Remove-CsCertificate mit dem Parameter-Previous problemlos entfernt werden.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein OAuthTokenIssuer-Zertifikat mit einem-Rollen-und-EffectiveDate-Parameter

1. Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.
    
2. Fordern Sie ein Verlängerungs-oder neues OAuthTokenIssuer-Zertifikat mit exportier barem privaten Schlüssel für das vorhandene Zertifikat auf dem Front-End-Server an.
    
3. Importieren Sie das neue OAuthTokenIssuer-Zertifikat in einen Front-End-Server in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben). Das OAuthTokenIssuer-Zertifikat wird global repliziert und muss auf den Servern in Ihrer Bereitstellung aktualisiert und erneuert werden. Als Beispiel wird der Front-End-Server verwendet.
    
4. Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet "Satz-CsCertificate", und verwenden Sie den Parameter "-Rolle" mit dem Parameter-EffectiveDate. Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus mindestens 24 Stunden festgelegt werden. 
    
    Der Befehl "Satz-CsCertificate" mit dem Parameter "-Rolle" und "-effektiv":
    
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
> Die EffectiveDate muss so formatiert sein, dass Sie den Regions-und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet. 
  
Wird das Gültigkeitsdatum (21.07.2015 01:00:00 Uhr) erreicht, werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2015 14:00:00 Uhr), werden Token nur durch das neue Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets Remove-CsCertificate mit dem Parameter-Previous problemlos entfernt werden.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
