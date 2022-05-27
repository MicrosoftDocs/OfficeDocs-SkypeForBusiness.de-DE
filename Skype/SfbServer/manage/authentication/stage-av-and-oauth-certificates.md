---
title: Bereitstellen von AV- und OAuth-Zertifikaten in Skype for Business Server mithilfe von -Roll in Set-CsCertificate
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: fda09cb53b664419d9652a0b663c83adc770c5cf
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674607"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Bereitstellen von AV- und OAuth-Zertifikaten in Skype for Business Server mithilfe von -Roll in Set-CsCertificate

**Zusammenfassung:** Bereitstellen von AV- und OAuth-Zertifikaten für Skype for Business Server.

Die Audio-/Videokommunikation (A/V) ist eine wichtige Komponente der Skype for Business Server. Features wie Anwendungsfreigabe und Audio- und Videokonferenzen basieren auf den Zertifikaten, die dem A/V-Edgedienst zugewiesen sind, insbesondere dem A/V-Authentifizierungsdienst.

> [!IMPORTANT]
> Dieses neue Feature ist für den A/V-Edgedienst und das OAuthTokenIssuer-Zertifikat ausgelegt. Andere Zertifikattypen können zusammen mit dem A/V-Edgedienst und dem OAuth-Zertifikattyp bereitgestellt werden, profitieren jedoch nicht vom Koexistenzverhalten, das das A/V-Edgedienstzertifikat ausführt.

Die Skype for Business Server-Verwaltungsshell-PowerShell-Cmdlets, die zum Verwalten Skype for Business Server Zertifikate verwendet werden, beziehen sich auf das A/V-Edgedienstzertifikat als AudioVideoAuthentication-Zertifikattyp und das OAuthServer-Zertifikat als typeOAuthTokenIssuer. Für den Rest dieses Themas und um die Zertifikate eindeutig zu identifizieren, werden sie vom gleichen Bezeichnertyp, AudioVideoAuthentication undOAuthTokenIssuer, verwendet.

Der A/V-Authentifizierungsdienst ist für die Ausgabe von Token verantwortlich, die von Clients und anderen A/V-Verbrauchern verwendet werden. Die Token werden aus Attributen auf dem Zertifikat generiert, und wenn das Zertifikat abläuft, führt der Verlust der Verbindung und die Anforderung, erneut mit einem neuen Token zusammenzuschließen, das vom neuen Zertifikat generiert wird. Ein neues Feature in Skype for Business Server wird dieses Problem beheben: die Möglichkeit, ein neues Zertifikat vor ablaufendem alten Zertifikat zu inszenieren und beide Zertifikate für einen bestimmten Zeitraum weiterhin funktionsfähig zu lassen. Dieses Feature verwendet aktualisierte Funktionen im Cmdlet Set-CsCertificate Skype for Business Server Verwaltungsshell. Der neue Parameter "-Roll" mit dem vorhandenen Parameter "-EffectiveDate" platziert das neue AudioVideoAuthentication-Zertifikat im Zertifikatspeicher. Das ältere AudioVideoAuthentication-Zertifikat verbleibt weiterhin, damit ausgestellte Token überprüft werden. Beginnend mit dem Einfügen des neuen AudioVideoAuthentication-Zertifikats tritt die folgende Ereignisreihe auf:

> [!TIP]
> Mithilfe der Skype for Business Server-Verwaltungsshell-Cmdlets zum Verwalten von Zertifikaten können Sie separate und unterschiedliche Zertifikate für jeden Zweck auf dem Edgeserver anfordern. Die Verwendung des Zertifikat-Assistenten im Skype for Business Server-Bereitstellungs-Assistenten unterstützt Sie beim Erstellen von Zertifikaten, weist jedoch in der Regel den **Standardtyp** auf, der alle Zertifikatsverwendungen für den Edgeserver mit einem einzelnen Zertifikat verbindet. Die empfohlene Vorgehensweise, wenn Sie das Feature für rollierende Zertifikate verwenden, besteht darin, das AudioVideoAuthentication-Zertifikat von den anderen Zertifikatzwecken zu entkoppeln. Sie können ein Zertifikat vom Standardtyp bereitstellen und bereitstellen, aber nur der AudioVideoAuthentication-Teil des kombinierten Zertifikats profitiert vom Staging. Ein Benutzer, der an einer Chatunterhaltung beteiligt ist, wenn das Zertifikat abläuft, muss sich abmelden und wieder anmelden, um das neue Zertifikat zu verwenden, das dem Access Edge-Dienst zugeordnet ist. Ähnliches Verhalten tritt für einen Benutzer auf, der mithilfe des Webkonferenz-Edgediensts an einer Webkonferenz beteiligt ist. Das OAuthTokenIssuer-Zertifikat ist ein bestimmter Typ, der auf allen Servern gemeinsam verwendet wird. Sie erstellen und verwalten das Zertifikat an einem Zentralen Ort, und das Zertifikat wird im zentralen Verwaltungsspeicher für alle anderen Server gespeichert.

Zusätzliche Informationen werden benötigt, um die Optionen und Anforderungen bei der Verwendung des Set-CsCertificate-Cmdlet zum Bereitstellen von Zertifikaten vor dem Ablauf des aktuellen Zertifikats nachvollziehen zu können. Der Parameter "-Roll" ist wichtig, aber im Wesentlichen ein einziger Zweck. Wenn Sie es als Parameter definieren, informieren Sie Set-CsCertificate, dass Sie Informationen über das Zertifikat bereitstellen, das von -Type (z. B. AudioVideoAuthentication und OAuthTokenIssuer) definiert wird, wenn das Zertifikat durch -EffectiveDate definiert wird.

 **-Roll**: Der Parameter "-Roll" ist erforderlich und weist Abhängigkeiten auf, die zusammen mit dem Parameter bereitgestellt werden müssen. Parameter, die zum Festlegen der betroffenen Zertifikate und ihrer Anwendungsweise erforderlich sind:

 **-EffectiveDate**: Der Parameter -EffectiveDate definiert, wann das neue Zertifikat mit dem aktuellen Zertifikat gemeinsam aktiv wird. Das "-EffectiveDate" kann sich in der Nähe der Ablaufzeit des aktuellen Zertifikats befinden, oder es kann einen längeren Zeitraum haben. Ein empfohlenes Mindest-EffectiveDate für das AudioVideoAuthentication-Zertifikat würde 8 Stunden betragen, was die Standardtokenlebensdauer für AV Edge-Diensttoken darstellt, die mit dem AudioVideoAuthentication-Zertifikat ausgegeben wurden.

Für das Bereitstellen der OAuthTokenIssuer-Zertifikate liegen verschiedene Anforderungen für die Durchlaufzeit vor, bevor das Zertifikat wirksam werden kann. Der Mindestwert des OAuthTokenIssuer-Zertifikats für die Durchlaufzeit sollte 24 Stunden vor der Ablaufzeit des aktuellen Zertifikats betragen. Die erweiterte Durchlaufzeit für die Koexistenz ist durch andere Serverrollen begründet, die von dem OAuthTokenIssuer-Zertifikat (beispielsweise Exchange Server) abhängen, das eine längere Aufbewahrungszeit für durch Zertifikate erstellte Authentifizierungs- und Verschlüsselungsschlüsselelemente besitzt.

 **-Thumbprint**: Beim Fingerabdruck handelt es sich um ein für dieses Zertifikat eindeutiges Attribut. Der Parameter "-Thumbprint" wird verwendet, um das Zertifikat zu identifizieren, das von den Aktionen des cmdlets Set-CsCertificate betroffen ist.

 **-Type**: Der Parameter "-Type" kann einen einzelnen Zertifikatverwendungstyp oder eine durch Kommas getrennte Liste von Zertifikatverwendungstypen akzeptieren. Die Zertifikattypen geben für das Cmdlet und den Server an, worin der Zweck des Zertifikats besteht. Beispielsweise ist der Typ "AudioVideoAuthentication" für die Verwendung durch den A/V-Edgedienst und den AV-Authentifizierungsdienst vorgesehen. Wenn Sie verschiedene Zertifikattypen zum gleichen Zeitpunkt bereitstellen möchten, müssen Sie die längste effektive Mindestdurchlaufzeit für die Zertifikate berücksichtigen. Sie müssen beispielsweise Zertifikate vom Typ "AudioVideoAuthentication" und Typ "OAuthTokenIssuer" bereitstellen. Ihr Minimum -EffectiveDate muss der größere der beiden Zertifikate sein, in diesem Fall der OAuthTokenIssuer, der eine minimale Vorlaufzeit von 24 Stunden hat. Wenn Sie das Zertifikat "AudioVideoAuthentication" nicht mit einer Durchlaufzeit von 24 Stunden bereitstellen möchten, stellen Sie es separat mit einem Ihren Anforderungen entsprechenden Wert für "EffectiveDate" bereit.

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein A/V-Edgedienstzertifikat mit den Parametern -Roll und -EffectiveDate

1. Melden Sie sich beim lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2. Fordern Sie eine Verlängerung oder ein neues AudioVideoAuthentication-Zertifikat mit exportierbarem privatem Schlüssel für das vorhandene Zertifikat im A/V-Edgedienst an.

3. Importieren Sie das neue AudioVideoAuthentication-Zertifikat auf den Edgeserver und alle anderen Edgeserver in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben).

4. Konfigurieren Sie das importierte Zertifikat mit dem cmdlet Set-CsCertificate, und verwenden Sie den Parameter "-Roll" mit dem Parameter "-EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden. Dies gibt uns eine Zeit, zu der das Zertifikat auf aktiv festgelegt werden muss, und ist das -EffectiveDate \<string\>: "22.07.2015 6:00:00 Uhr".

   > [!IMPORTANT]
   > Für einen Edgepool müssen alle AudioVideoAuthentication-Zertifikate bereitgestellt und nach dem Datum und der Uhrzeit bereitgestellt werden, die durch den Parameter "-EffectiveDate" des ersten bereitgestellten Zertifikats definiert sind, um mögliche Unterbrechungen der A/V-Kommunikation aufgrund des ablaufenden älteren Zertifikats zu vermeiden, bevor alle Client- und Consumertoken mithilfe des neuen Zertifikats erneuert wurden.

   Der Befehl Set-CsCertificate mit dem Parameter "-Roll" und "-EffectiveTime":

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
   ```

   Ein Set-CsCertificate-Beispielbefehl:

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015 6:00:00 AM"
   ```

    > [!IMPORTANT]
    > Das EffectiveDate muss so formatiert sein, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.

Um den Prozess weiter zu verstehen, den Set-CsCertificate, -Roll und -EffectiveDate verwenden, um ein neues Zertifikat für die Ausgabe neuer AudioVideoAuthentication-Token auszustellen, während weiterhin ein vorhandenes Zertifikat verwendet wird, um audioVideoAuthentication zu überprüfen, die von Verbrauchern verwendet werden, ist eine visuelle Zeitachse ein effektives Mittel zum Verständnis des Prozesses. Im folgenden Beispiel ermittelt der Administrator, dass das A/V Edge-Dienstzertifikat am 22.07.2015 um 14:00:00 Uhr abläuft. Er fordert ein neues Zertifikat an und erhält es und importiert es auf jeden Edgeserver in seinem Pool. Um 2 Uhr am 22.07.2015 beginnt er mit der Ausführung Get-CsCertificate mit -Roll, -Thumbprint gleich der Fingerabdruckzeichenfolge des neuen Zertifikats und -EffectiveTime auf 22.07.2015 6:00:00 Uhr festgelegt. Er führt diesen Befehl auf jedem Edgeserver aus.

![Verwenden der Parameter "Roll" und "EffectiveDate".](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)

|Beschriftung|Stufe 1|
|:-----|:-----|
|1|Start: 22.07.2015 12:00:00 Uhr  <br/> Das aktuelle AudioVideoAuthentication-Zertifikat läuft am 22.07.2015 um 14:00:00 Uhr ab. Dies wird durch den Ablaufzeitstempel des Zertifikats bestimmt. Planen Sie den Austausch und den Rollover Ihres Zertifikats so, dass eine Überlappung von 8 Stunden (Standardtokenlebensdauer) berücksichtigt wird, bevor das vorhandene Zertifikat den Ablaufzeitpunkt erreicht. In diesem Beispiel wird die Vorlaufzeit von 02:00:00 Uhr verwendet, damit der Administrator genügend Zeit zum Platzieren und Bereitstellen der neuen Zertifikate vor der Effektiven Zeit von 6:00:00 Uhr hat.|
|2|22.07.2015 02:00:00 - 22.07.2015 5:59:59  <br/> Festlegen von Zertifikaten auf Edgeservern mit einer Effektiven Zeit von 6:00:00 Uhr (4 Stunden Vorlaufzeit ist für dieses Beispiel, kann aber länger sein) mit Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate \<datetime string of the effective time for new certificate\>|
|3|22.07.2015 6:00 - 22.07.2015 14:00 Uhr  <br/> Um Token zu überprüfen, wird zuerst das neue Zertifikat ausprobiert, und wenn das neue Zertifikat das Token nicht überprüfen kann, wird das alte Zertifikat ausprobiert. Dieser Prozess wird für alle Token während des Überlappungszeitraums von 8 Stunden (Standardtokenlebensdauer) verwendet.|
|4|Ende: 22.07.2015 14:00:01  <br/> Das alte Zertifikat ist abgelaufen, und das neue Zertifikat wurde übernommen. Altes Zertifikat kann mit Remove-CsCertificate -Type \<certificate usage type\> -Previous sicher entfernt werden|

Wenn die Effektive Zeit erreicht ist (22.07.2015 06:00:00 Uhr), werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2015 14:00:00 Uhr), werden Token nur vom neuen Zertifikat überprüft. Das alte Zertifikat kann mit dem cmdlet Remove-CsCertificate mit dem Parameter -Previous sicher entfernt werden.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein OAuthTokenIssuer-Zertifikat mit den Parametern -Roll und -EffectiveDate

1. Melden Sie sich beim lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2. Fordern Sie eine Verlängerung oder ein neues OAuthTokenIssuer-Zertifikat mit exportierbarem privatem Schlüssel für das vorhandene Zertifikat auf dem Front-End-Server an.

3. Importieren Sie das neue OAuthTokenIssuer-Zertifikat auf einen Front-End-Server in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben). Das OAuthTokenIssuer-Zertifikat wird global repliziert und muss auf den Servern in Ihrer Bereitstellung aktualisiert und erneuert werden. Der Front-End-Server wird als Beispiel verwendet.

4. Konfigurieren Sie das importierte Zertifikat mit dem cmdlet Set-CsCertificate, und verwenden Sie den Parameter "-Roll" mit dem Parameter "-EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden.

    Der Befehl Set-CsCertificate mit dem Parameter "-Roll" und "-EffectiveTime":

   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumbprint of new certificate> -Roll -EffectiveDate <date and time for certificate to become active> -identity Global
   ```

Ein Set-CsCertificate-Beispielbefehl:

  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015 1:00:00 PM"
  ```

> [!IMPORTANT]
> Das EffectiveDate muss so formatiert sein, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.

Wenn die effektive Zeit erreicht ist (21.07.2015 01:00:00 Uhr), werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2015 14:00:00 Uhr), werden Token nur vom neuen Zertifikat überprüft. Das alte Zertifikat kann mit dem cmdlet Remove-CsCertificate mit dem Parameter -Previous sicher entfernt werden.

```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous
```

## <a name="see-also"></a>Siehe auch

[Verwalten der Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate)

[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate)
