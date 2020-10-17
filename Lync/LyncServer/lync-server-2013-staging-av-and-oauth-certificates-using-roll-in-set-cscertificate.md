---
title: Staging von AV-und OAuth-Zertifikaten mithilfe von-Roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 003c8da4c953dc843fe49bf3fc5eb2d2a70b093b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533012"
---
# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Staging von AV-und OAuth-Zertifikaten in lync Server 2013 using-Roll in Set-CsCertificate

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-13_

Die Kommunikation zwischen Audio und Video (a/V) ist eine wichtige Komponente von Microsoft lync Server 2013. Features wie Anwendungsfreigabe und Audio-und Videokonferenzen basieren auf den Zertifikaten, die dem A/V-Edgedienst zugewiesen sind, insbesondere dem A/V-Authentifizierungsdienst.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Dieses neue Feature wurde für die A/V-Edgedienst und das <EM>OAuthTokenIssuer</EM> -Zertifikat entwickelt. Andere Zertifikattypen können zusammen mit dem A/V-Edgedienst-und OAuth-Zertifikattyp bereitgestellt werden, profitieren jedoch nicht von dem Verhalten der Koexistenz, das das A/V-Edgedienst Zertifikat enthält.</P>
> <LI>
> <P>Die lync Server-Verwaltungsshell PowerShell-Cmdlets, mit denen Microsoft lync Server 2013 Zertifikate verwaltet werden, bezieht sich auf das A/V-Edgedienst Zertifikat als <EM>AudioVideoAuthentication</EM> -Zertifikattyp und das OAuthServer-Zertifikat als Typ <EM>OAuthTokenIssuer</EM>. Für den Rest dieses Themas und zur eindeutigen Identifizierung der Zertifikate werden diese von demselben Bezeichnertyp, <EM>AudioVideoAuthentication</EM> und <EM>OAuthTokenIssuer</EM>, referenziert.</P></LI></OL>



</div>

Der a/v-Authentifizierungsdienst ist für die Ausstellung von Token verantwortlich, die von Clients und anderen a/v-Consumern verwendet werden. Die Token werden aus Attributen auf dem Zertifikat generiert, und wenn das Zertifikat abläuft, resultieren Verbindungsverlust und Anforderung zum erneuten Beitritt mit einem neuen Token, das vom neuen Zertifikat generiert wird. Durch ein neues Feature in lync Server 2013 wird dieses Problem behoben – die Möglichkeit, ein neues Zertifikat im Vorfeld des alten zu inszenieren und zu ermöglichen, dass beide Zertifikate für einen bestimmten Zeitraum weiterhin funktionsfähig sind. Dieses Feature verwendet aktualisierte Funktionen im Cmdlet Set-CsCertificate lync Server-Verwaltungsshell. Der neue Parameter – Roll mit dem vorhandenen Parameter – EffectiveDate ", platziert das neue AudioVideoAuthentication-Zertifikat im Zertifikatspeicher. Das ältere AudioVideoAuthentication-Zertifikat bleibt weiterhin für ausgestellte Token erhalten, für die validiert werden soll. Beginnend mit dem Setzen des neuen AudioVideoAuthentication-Zertifikats wird die folgende Reihe von Ereignissen ausgeführt:

<div>


> [!TIP]
> Mithilfe der lync Server-Verwaltungsshell-Cmdlets zum Verwalten von Zertifikaten können Sie separate und unterschiedliche Zertifikate für jeden Zweck auf dem Edgeserver anfordern. Die Verwendung des Zertifikat-Assistenten im lync Server Bereitstellungs-Assistenten unterstützt Sie beim Erstellen von Zertifikaten, ist in der Regel jedoch der <STRONG>Standardtyp</STRONG> , bei dem alle Zertifikat Verwendungen für das Edgeserver auf ein einzelnes Zertifikat verwendet werden. Die empfohlene Vorgehensweise bei der Verwendung des Features für das parallele Zertifikat besteht darin, das AudioVideoAuthentication-Zertifikat von den anderen Zertifikats Zwecken zu entkoppeln. Sie können ein Zertifikat des Standardtyps bereitstellen und inszenieren, aber nur der AudioVideoAuthentication-Teil des kombinierten Zertifikats profitiert von der stagingfunktion. Ein Benutzer, der an einer (beispielsweise) Chatnachrichten Unterhaltung beteiligt ist, wenn das Zertifikat abläuft, muss sich abmelden und wieder anmelden, um das dem Zugriffs-Edgedienst zugeordnete neue Zertifikat verwenden zu können. Ein ähnliches Verhalten tritt für einen Benutzer auf, der an einer Webkonferenz beteiligt ist, indem Sie das Webkonferenz-Edgedienst verwenden. Das OAuthTokenIssuer-Zertifikat ist ein bestimmter Typ, der für alle Server freigegeben ist. Sie erstellen und verwalten das Zertifikat an einer einzigen Stelle, und das Zertifikat wird im zentralen Verwaltungsspeicher für alle anderen Server gespeichert.



</div>

Zusätzliche Informationen werden benötigt, um die Optionen und Anforderungen bei der Verwendung des Set-CsCertificate-Cmdlet zum Bereitstellen von Zertifikaten vor dem Ablauf des aktuellen Zertifikats nachvollziehen zu können. Der Parameter "–Roll" ist wichtig, dient jedoch nur einem Zweck. Wenn Sie es als Parameter definieren, sagen Sie Set-CsCertificate, dass Sie Informationen zu dem Zertifikat bereitstellen, das von – Type (beispielsweise AudioVideoAuthentication und OAuthTokenIssuer) betroffen sein wird, wenn das Zertifikat durch – EffectiveDate "definiert wird.

**-Roll:** Der-Roll-Parameter ist erforderlich und enthält Abhängigkeiten, die zusammen mit ihm angegeben werden müssen. Parameter, die zum Festlegen der betroffenen Zertifikate und ihrer Anwendungsweise erforderlich sind:

**-EffectiveDate ":** Der Parameter – EffectiveDate "definiert, wann das neue Zertifikat zusammen mit dem aktuellen Zertifikat Co-aktiv werden soll. Die – EffectiveDate "kann nahe der Ablaufzeit des aktuellen Zertifikats liegen, oder es kann einen längeren Zeitraum dauern. Ein empfohlenes Minimum – EffectiveDate "für das AudioVideoAuthentication-Zertifikat wäre 8 Stunden, was die Standard Gültigkeitsdauer des Tokens für AV-Edgedienst-Token ist, die mit dem AudioVideoAuthentication-Zertifikat ausgegeben werden.

Für das Bereitstellen der OAuthTokenIssuer-Zertifikate liegen verschiedene Anforderungen für die Durchlaufzeit vor, bevor das Zertifikat wirksam werden kann. Der Mindestwert des OAuthTokenIssuer-Zertifikats für die Durchlaufzeit sollte 24 Stunden vor der Ablaufzeit des aktuellen Zertifikats betragen. Die erweiterte Durchlaufzeit für die Koexistenz ist durch andere Serverrollen begründet, die von dem OAuthTokenIssuer-Zertifikat (beispielsweise Exchange Server) abhängen, das eine längere Aufbewahrungszeit für durch Zertifikate erstellte Authentifizierungs- und Verschlüsselungsschlüsselelemente besitzt.

**-Fingerabdruck:** Bei dem Fingerabdruck handelt es sich um ein Attribut des Zertifikats, das für dieses Zertifikat eindeutig ist. Mit dem Parameter "–Thumbprint" wir das Zertifikat ermittelt, das von den Aktionen des Cmdlets "Set-CsCertificate" betroffen ist.

**-Geben Sie Folgendes ein:** Der Parameter – Type kann einen einzelnen Zertifikat Verwendungstyp oder eine durch trennzeichengetrennte Liste mit Zertifikat Verwendungstypen akzeptieren. Die Zertifikattypen geben für das Cmdlet und den Server an, worin der Zweck des Zertifikats besteht. Geben Sie beispielsweise AudioVideoAuthentication für die Verwendung durch den A/V-Edgedienst und den AV-Authentifizierungsdienst ein. Wenn Sie verschiedene Zertifikattypen zum gleichen Zeitpunkt bereitstellen möchten, müssen Sie die längste effektive Mindestdurchlaufzeit für die Zertifikate berücksichtigen. Sie müssen beispielsweise Zertifikate vom Typ "AudioVideoAuthentication" und Typ "OAuthTokenIssuer" bereitstellen. Als Mindestwert muss für "–EffectiveDate" der höhere Wert der beiden Zertifikate festgelegt werden, in diesem Fall der Wert des Zertifikats "OAuthTokenIssuer", dessen Mindestdurchlaufzeit 24 Stunden beträgt. Wenn Sie das Zertifikat "AudioVideoAuthentication" nicht mit einer Durchlaufzeit von 24 Stunden bereitstellen möchten, stellen Sie es separat mit einem Ihren Anforderungen entsprechenden Wert für "EffectiveDate" bereit.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuern Sie ein A/V-Edgedienst-Zertifikat mit den Parametern "– Roll" und "-EffectiveDate" "

1.  Melden Sie sich beim lokalen Computer als Mitglied der Gruppe Administratoren an.

2.  Fordern Sie ein Erneuerungs-oder neues AudioVideoAuthentication-Zertifikat mit exportier barem privaten Schlüssel für das vorhandene Zertifikat im A/V-Edgedienst an.

3.  Importieren Sie das neue AudioVideoAuthentication-Zertifikat in den Edgeserver und alle anderen Edgeserver in Ihrem Pool (sofern ein Pool bereitgestellt wurde).

4.  Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet "Set-CsCertificate", und verwenden Sie den Parameter "–Roll" mit dem Parameter "–EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden. Dies gibt uns eine Zeit, für die das Zertifikat auf aktiv festgelegt werden muss, und ist der-EffectiveDate " \<string\> :" 7/22/2012 6:00:00 am ".
    
    <div>
    

    > [!IMPORTANT]
    > Für eine Edgepool müssen Sie alle AudioVideoAuthentication-Zertifikate bereitstellen und mit dem Datum und der Uhrzeit bereitstellen, die durch den Parameter – EffectiveDate "des ersten bereitgestellten Zertifikats definiert wurden, um mögliche A/V-KOMMUNIKATIONSUNTERBRECHUNGEN zu vermeiden, da das ältere Zertifikat abläuft, bevor alle Client-und Consumer-Token mithilfe des neuen Zertifikats erneuert wurden.

    
    </div>
    
    Der Befehl "Set-CsCertificate" mit den Parametern "–Roll" und "–EffectiveTime":
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Ein Set-CsCertificate-Beispielbefehl:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > Das Gültigkeitsdatum muss so formatiert werden, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.

    
    </div>

Mit einer optischen Zeitachse können Sie den besser verstehen, der von "Set-CsCertificate", "-Roll" und "–EffectiveDate" zum Bereitstellen eines neuen Zertifikats für die Aussstellung neuer AudioVideoAuthentication-Token verwendet wird, während weiterhin mit einem vorhandenen Zertifikat das von Benutzern verwendete AudioVideoAuthentication-Zertifikat validiert wird.

Im folgenden Beispiel bestimmt der Administrator, dass das A/V-Edgedienst Zertifikat um 2:00:00 Uhr am 07/22/2012 abläuft. Er fordert und empfängt ein neues Zertifikat und importiert es in jeden Edgeserver in seinem Pool. Am 22.07.2012 um 14 Uhr startet er die Ausführung von "Get-CsCertificate" mit "–Roll", "-Thumbprint" (dieser Wert entspricht der Fingerabdruckzeichenfolge des neuen Zertifikats) und "–EffectiveTime" (für diesen Wert ist 22.07.2012 6:00:00 Uhr festgelegt). Er führt diesen Befehl für jede Edgeserver aus.

![Verwenden der Parameter "Roll" und "EffectiveDate" ".](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Verwenden der Parameter "Roll" und "EffectiveDate" ".")

Wird das Gültigkeitsdatum (22.07.2012 6:00:00 Uhr) erreicht, werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2012 14:00:00 Uhr), werden Token nur durch das neue Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets "Remove-CsCertificate" mit dem Parameter "–Previous" sicher entfernt werden.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>So aktualisieren oder erneuen Sie ein OAuthTokenIssuer-Zertifikat mit den Parametern "–Roll" und "-EffectiveDate"

1.  Melden Sie sich beim lokalen Computer als Mitglied der Gruppe Administratoren an.

2.  Fordern Sie ein Erneuerungs-oder neues OAuthTokenIssuer-Zertifikat mit exportier barem privaten Schlüssel für das vorhandene Zertifikat im A/V-Edgedienst an.

3.  Importieren Sie das neue OAuthTokenIssuer-Zertifikat in einen Front-End-Server in Ihrem Pool (sofern ein Pool bereitgestellt wurde). Das OAuthTokenIssuer-Zertifikat wird global repliziert und muss auf den Servern in Ihrer Bereitstellung aktualisiert und erneuert werden. Die Front-End-Server wird als Beispiel verwendet.

4.  Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet "Set-CsCertificate", und verwenden Sie den Parameter "–Roll" mit dem Parameter "–EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden.
    
    Der Befehl "Set-CsCertificate" mit den Parametern "–Roll" und "–EffectiveTime":
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Ein Set-CsCertificate-Beispielbefehl:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > Das Gültigkeitsdatum muss so formatiert werden, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.

    
    </div>

Wird das Gültigkeitsdatum (21.07.2012 01:00:00 Uhr) erreicht, werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2012 14:00:00 Uhr), werden Token nur durch das neue Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets "Remove-CsCertificate" mit dem Parameter "–Previous" sicher entfernt werden.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Edgeserver Zertifikaten in lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Einrichten von Edge-Zertifikaten für lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Gruppe-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

