---
title: Staging von AV-und OAuth-Zertifikaten mithilfe von-Rolle in der Gruppe-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4acdf759181dee3df872c7803ec595c63fb07016
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Rolle in der Gruppe-CsCertificate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-13_

Audio/Video (a/V)-Kommunikation ist eine wichtige Komponente von Microsoft lync Server 2013. Features wie Anwendungsfreigabe und Audio-und Videokonferenzen basieren auf den Zertifikaten, die dem a/v-Edgedienst, insbesondere dem a/v-Authentifizierungsdienst, zugewiesen sind.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Dieses neue Feature ist für den A/V-Edgedienst und das <EM>OAuthTokenIssuer</EM> -Zertifikat konzipiert. Andere Zertifikattypen können zusammen mit dem a/v-Edgedienst und dem OAuth-Zertifikattyp bereitgestellt werden, profitieren aber nicht vom Koexistenzsystem, das vom a/v-Edgedienst-Zertifikat bereitgestellt wird.</P>
> <LI>
> <P>Die in der lync Server-Verwaltungsshell verwendeten PowerShell-Cmdlets für die Verwaltung von Microsoft lync Server 2013-Zertifikaten bezieht sich auf das A/V-Edgedienst Zertifikat als <EM>AudioVideoAuthentication</EM> -Zertifikattyp und das OAuthServer-Zertifikat als Typ <EM> OAuthTokenIssuer</EM>. Im restlichen Thema – und zur eindeutigen Identifizierung der Zertifikate – wird mit demselben ID-Typ, <EM>AudioVideoAuthentication</EM> und <EM>OAuthTokenIssuer</EM>, auf sie verwiesen.</P></LI></OL>



</div>

Der a/v-Authentifizierungsdienst ist für das Ausgeben von Token verantwortlich, die von Clients und anderen a/v-Consumern verwendet werden. Die Token werden aus Attributen auf dem Zertifikat generiert, und wenn das Zertifikat abläuft, führt dies zu einem Verbindungsabbruch und einer Anforderung, erneut mit einem neuen Token zu verbinden, das vom neuen Zertifikat generiert wird. Ein neues Feature in lync Server 2013 wird dieses Problem lindern – die Möglichkeit, ein neues Zertifikat im Vorfeld des alten zu inszenieren, das abläuft und es ermöglicht, dass beide Zertifikate während eines bestimmten Zeitraums weiterhin funktionieren. Dieses Feature verwendet aktualisierte Funktionen im Cmdlet "CsCertificate" der lync Server-Verwaltungsshell. Mit dem neuen Parameter – Rolle, mit dem vorhandenen Parameter – EffectiveDate, wird das neue AudioVideoAuthentication-Zertifikat im Zertifikatspeicher platziert. Das ältere AudioVideoAuthentication-Zertifikat bleibt für ausgestellte Token weiterhin gültig. Beginnend mit dem Setzen des neuen AudioVideoAuthentication-Zertifikats wird die folgende Reihe von Ereignissen auftreten:

<div>


> [!TIP]
> Mithilfe der lync Server-Verwaltungsshell-Cmdlets für die Verwaltung von Zertifikaten können Sie für jeden Zweck auf dem Edgeserver getrennte und unterschiedliche Zertifikate anfordern. Die Verwendung des Zertifikat-Assistenten im lync Server-Bereitstellungs-Assistenten unterstützt Sie beim Erstellen von Zertifikaten, <STRONG></STRONG> ist in der Regel aber der Standardtyp, mit dem alle Zertifikat Verwendungen für den Edgeserver auf einem einzigen Zertifikat kombiniert werden. Die empfohlene Vorgehensweise bei Verwendung der Funktion für rollende Zertifikate besteht darin, das AudioVideoAuthentication-Zertifikat von den anderen Zertifikatzwecken zu lösen. Sie können ein Zertifikat vom Typ „Standard“ bereitstellen, doch nur der AudioVideoAuthentication-Teil des kombinierten Zertifikats profitiert von dem Staging. Ein Benutzer, der an (beispielsweise) einer Sofortnachrichtenunterhaltung teilhat, wenn das Zertifikat abläuft, muss sich abmelden und wieder anmelden, um das neue Zertifikat zu verwenden, das dem Access Edge-Dienst zugeordnet ist. Ein ähnliches Verhalten tritt für einen Benutzer ein, der mit dem Webkonferenz-Edgedienst an einer Webkonferenz teilnimmt. Das OAuthTokenIssuer-Zertifikat ist ein bestimmter Typ, der auf allen Servern freigegeben ist. Sie erstellen und verwalten das Zertifikat an einer zentralen Stelle, und das Zertifikat wird im zentralen Verwaltungsspeicher für alle anderen Server gespeichert.



</div>

Zusätzliche Informationen werden benötigt, um die Optionen und Anforderungen bei der Verwendung des Set-CsCertificate-Cmdlets zum Bereitstellen von Zertifikaten vor dem Ablauf des aktuellen Zertifikats nachvollziehen zu können. Der Parameter „–Roll“ ist wichtig, dient jedoch nur einem Zweck. Wenn Sie ihn als Parameter festlegen, informieren Sie damit „Set-CsCertificate“, dass Sie Informationen zum betroffenen durch „–Type“ definierten Zertifikat (z. B. AudioVideoAuthentication und OAuthTokenIssuer) bereitstellen werden, wenn es am durch „–EffectiveDate“ definierten Zeitpunkt gültig wird.

**-Rolle:** Der-Rolle-Parameter ist erforderlich und weist Abhängigkeiten auf, die zusammen mit ihm bereitgestellt werden müssen. Parameter, die zum Festlegen der betroffenen Zertifikate und ihrer Anwendungsweise erforderlich sind:

**-EffectiveDate:** Der Parameter – EffectiveDate definiert, wann das neue Zertifikat mit dem aktuellen Zertifikat gemeinsam aktiv wird. Die – EffectiveDate kann in der Nähe der Ablaufzeit des aktuellen Zertifikats liegen, oder es kann einen längeren Zeitraum dauern. Ein Empfohlenes Mindest-EffectiveDate für das AudioVideoAuthentication-Zertifikat wäre 8 Stunden, was die standardmäßige Token-Lebensdauer für AV-Edgedienst-Token ist, die mit dem AudioVideoAuthentication-Zertifikat ausgegeben werden.

Für das Bereitstellen der OAuthTokenIssuer-Zertifikate liegen verschiedene Anforderungen für die Vorlaufzeit vor, bevor das Zertifikat wirksam werden kann. Der Mindestwert des OAuthTokenIssuer-Zertifikats für die Vorlaufzeit sollte 24 Stunden vor der Ablaufzeit des aktuellen Zertifikats betragen. Die erweiterte Vorlaufzeit für die Koexistenz ist durch andere Serverrollen begründet, die von dem OAuthTokenIssuer-Zertifikat (beispielsweise Exchange Server) abhängen, das eine längere Aufbewahrungszeit für durch Zertifikate erstellte Authentifizierungs- und Verschlüsselungsschlüsselelemente besitzt.

**-Fingerabdruck:** Der Fingerabdruck ist ein Attribut des Zertifikats, das für dieses Zertifikat eindeutig ist. Mit dem Parameter „–Thumbprint“ wird das Zertifikat ermittelt, das von den Aktionen des Cmdlets „Set-CsCertificate“ betroffen ist.

**-Geben Sie Folgendes ein:** Der Parameter – Type kann einen einzelnen Zertifikat Verwendungstyp oder eine durch trennzeichengetrennte Liste der Zertifikat Verwendungstypen akzeptieren. Die Zertifikattypen geben für das Cmdlet und den Server an, worin der Zweck des Zertifikats besteht. Geben Sie beispielsweise AudioVideoAuthentication ein, um den A/V-Edgedienst und den AV-Authentifizierungsdienst zu verwenden. Wenn Sie verschiedene Zertifikattypen zum gleichen Zeitpunkt bereitstellen möchten, müssen Sie die längste effektive Mindestvorlaufzeit für die Zertifikate berücksichtigen. Sie müssen beispielsweise Zertifikate vom Typ „AudioVideoAuthentication“ und vom Typ „OAuthTokenIssuer“ bereitstellen. Als Mindestwert muss für „-EffectiveDate“ der höhere Wert der beiden Zertifikate festgelegt werden, in diesem Fall der Wert des Zertifikats „OAuthTokenIssuer“, dessen Mindestvorlaufzeit 24 Stunden beträgt. Wenn Sie das Zertifikat „AudioVideoAuthentication“ nicht mit einer Vorlaufzeit von 24 Stunden bereitstellen möchten, stellen Sie es separat mit einem Ihren Anforderungen entsprechenden Wert für „EffectiveDate“ bereit.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein a/V-Edgedienst-Zertifikat mit einem – Rollen-und-EffectiveDate-Parameter

1.  Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2.  Fordern Sie ein Erneuerungs-oder neues AudioVideoAuthentication-Zertifikat mit exportier barem privaten Schlüssel für das vorhandene Zertifikat im a/V-Edgedienst an.

3.  Importieren Sie das neue AudioVideoAuthentication-Zertifikat auf den Edgeserver und alle anderen Edgeserver in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben).

4.  Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet „Set-CsCertificate“ und verwenden Sie den Parameter „–Roll“ mit dem Parameter „–EffectiveDate“. Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokenlebensdauer (standardmäßig acht Stunden) festgelegt werden. Dadurch erhalten wir eine Uhrzeit, zu der das Zertifikat auf "aktiv" festgesetzt werden muss, \<und\>ist die Zeichenfolge – EffectiveDate: "7/22/2012 6:00:00 am".
    
    <div>
    

    > [!IMPORTANT]
    > Bei einem Edge-Pool müssen alle AudioVideoAuthentication-Zertifikate bereitgestellt und bis zu dem Datum und der Uhrzeit bereitgestellt werden, das durch den – EffectiveDate-Parameter des ersten bereitgestellten Zertifikats definiert ist, um mögliche A/V-KOMMUNIKATIONSUNTERBRECHUNGEN aufgrund des älteren zu vermeiden. Zertifikat läuft ab, bevor alle Client-und Consumer-Token mit dem neuen Zertifikat erneuert wurden.

    
    </div>
    
    Der Befehl „Set-CsCertificate“ mit den Parametern „–Roll“ und „–EffectiveTime“:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Ein Set-CsCertificate-Beispielbefehl:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > Das Gültigkeitsdatum muss so formatiert werden, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.

    
    </div>

Mit einer optischen Zeitachse können Sie den Vorgang besser verstehen, der von „Set-CsCertificate“, „-Roll“ und „–EffectiveDate“ zum Bereitstellen eines neuen Zertifikats für die Ausstellung neuer AudioVideoAuthentication-Token verwendet wird, während weiterhin mit einem vorhandenen Zertifikat das von Benutzern verwendete AudioVideoAuthentication-Zertifikat validiert wird.

Im folgenden Beispiel wird vom Administrator festgelegt, dass das A/V-Edgedienst-Zertifikat um 2:00:00 Uhr am 07/22/2012 abläuft. Er fordert und empfängt ein neues Zertifikat und importiert es auf jeden Edgeserver in seinem Pool. Um 2 Uhr auf 07/22/2012 beginnt er mit der Ausführung von Get-CsCertificate mit – Rolle,-Fingerabdruck, der der Fingerabdruck Zeichenfolge des neuen Zertifikats entspricht, und – Effektivzeit, die auf 07/22/2012 6:00:00 Uhr eingestellt ist. Er führt diesen Befehl auf jedem Edgeserver aus.

![Verwenden des Rollen-und des EffectiveDate-Parameters] (images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Verwenden des Rollen-und des EffectiveDate-Parameters")

Wenn die effektive Zeit erreicht ist (7/22/2012 6:00:00 Uhr), werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Nachdem das alte Zertifikat abgelaufen ist (7/22/2012 2:00:00 Uhr), werden Token nur vom neuen Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets „Remove-CsCertificate“ mit dem Parameter „–Previous“ sicher entfernt werden.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein OAuthTokenIssuer-Zertifikat mit einem – Rollen-und-EffectiveDate-Parameter

1.  Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2.  Fordern Sie ein Erneuerungs-oder neues OAuthTokenIssuer-Zertifikat mit exportier barem privaten Schlüssel für das vorhandene Zertifikat im a/V-Edgedienst an.

3.  Importieren Sie das neue OAuthTokenIssuer-Zertifikat in einen Front-End-Server in Ihrem Pool (wenn Sie einen Pool bereitgestellt haben). Das OAuthTokenIssuer-Zertifikat wird global repliziert und muss auf den Servern in Ihrer Bereitstellung aktualisiert und erneuert werden. Als Beispiel wird der Front-End-Server verwendet.

4.  Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet „Set-CsCertificate“ und verwenden Sie den Parameter „–Roll“ mit dem Parameter „–EffectiveDate“. Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus mindestens 24 Stunden festgelegt werden.
    
    Der Befehl „Set-CsCertificate“ mit den Parametern „–Roll“ und „–EffectiveTime“:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Ein Set-CsCertificate-Beispielbefehl:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > Das Gültigkeitsdatum muss so formatiert werden, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.

    
    </div>

Wenn die effektive Zeit erreicht ist (7/21/2012 1:00:00 Uhr), werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Nachdem das alte Zertifikat abgelaufen ist (7/22/2012 2:00:00 Uhr), werden Token nur vom neuen Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets „Remove-CsCertificate“ mit dem Parameter „–Previous“ sicher entfernt werden.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Edgeserver-Zertifikaten in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Einrichten von Edgezertifikaten für Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

