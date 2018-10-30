---
title: Bereitstellen von AV- und OAuth-Zertifikaten in Lync Server 2013 mithilfe von -Roll in Set-CsCertificate
TOCTitle: Bereitstellen von AV- und OAuth-Zertifikaten in Lync Server 2013 mithilfe von -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49890661
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von AV- und OAuth-Zertifikaten in Lync Server 2013 mithilfe von -Roll in Set-CsCertificate

 

_**Letztes Änderungsdatum des Themas:** 2012-11-13_

Die Audio-Video-Kommunikation ist eine wichtige Komponente von Microsoft Lync Server 2013. Funktionen wie die Anwendungsfreigabe und Audio-/Videokonferenzen basieren auf den dem A/V-Edgedienst zugewiesenen Zertifikaten, insbesondere der A/V-Authentifizierungsdienst.


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Die neue Funktion soll für den A/V-Edgedienst und das <EM>OAuthTokenIssuer</EM>-Zertifikat funktionieren. Andere Zertifikattypen können gemeinsam mit dem A/V-Edgedienst und dem OAuth-Zertifikattyp bereitgestellt werden, Sie profitieren jedoch nicht von dem Koexistenzverhalten des A/V-Edgedienst-Zertifikats.</P>
> <LI>
> <P>Die Lync Server-Verwaltungsshell PowerShell-Cmdlets, die zur Verwaltung der Microsoft Lync Server 2013-Zertifikate verwendet werden, beziehen sich auf das A/V-Edgedienst-Zertifikat als <EM>AudioVideoAuthentication</EM>-Zertifikattyp und das OAuthServer-Zertifikat als Typ <EM>OAuthTokenIssuer</EM>. Im restlichen Thema – und zur eindeutigen Identifizierung der Zertifikate – wird mit demselben ID-Typ, <EM>AudioVideoAuthentication</EM> und <EM>OAuthTokenIssuer</EM>, auf sie verwiesen.</P></LI></OL>



Der A/V-Authentifizierungsdienst ist für die Ausgabe von Token verantwortlich, die von Clients und anderen A/V-Benutzern verwendet werden. Die Token werden aus Attributen auf dem Zertifikat erstellt. Wenn das Zertifikat abläuft, geht die Verbindung verloren, und es muss eine Verbindung mit einem neuen Token (generiert vom neuen Zertifikat) hergestellt werden. Eine neue Funktion in Lync Server 2013 soll dieses Problem beheben: die Möglichkeit zum Bereitstellen eines neuen Zertifikats vor dem Ablauf des alten Zertifikats und die gleichzeitige Ausführung der Zertifikate für einen bestimmten Zeitraum. Diese Funktion verwendet aktualisierte Funktionalität im Lync Server-Verwaltungsshell-Cmdlet "Set-CsCertificate". Der neue Parameter "–Roll" legt zusammen mit dem vorhandenen Parameter "–EffectiveDate" das neue AudioVideoAuthentication-Zertifikat im Zertifikatspeicher ab. Das ältere AudioVideoAuthentication-Zertifikat bleibt für ausgestellte Token erhalten, mit denen sie validiert werden sollen. Beginnend beim Ablegen des neuen AudioVideoAuthentication-Zertifikats am richtigen Ort finden folgende Ereignisse statt:


> [!TIP]
> Mithilfe der Cmdlets der Lync Server-Verwaltungsshell zum Verwalten von Zertifikaten können Sie separate eigene Zertifikate für alle Zwecke auf dem Edgeserver anfordern. Der Zertifikat-Assistent im Lync Server-Bereitstellungs-Assistenten unterstützt Sie beim Erstellen von Zertifikaten, diese sind jedoch in der Regel vom Typ <STRONG>Standard</STRONG>, der alle Zertifikatverwendungen für den Edgeserver in einem einzigen Zertifikat zusammenfasst. Die empfohlene Vorgehensweise bei Verwendung der Funktion für rollende Zertifikate besteht darin, das AudioVideoAuthentication-Zertifikat von den anderen Zertifikatzwecken zu lösen. Sie können ein Zertifikat vom Typ "Standard" bereitstellen, doch nur der AudioVideoAuthentication-Teil des kombinierten Zertifikats profitiert von dem Staging. Ein Benutzer, der (beispielsweise) eine Instant&nbsp;Messaging-Unterhaltung führt, wenn das Zertifikat abläuft, muss sich ab- und wieder anmelden, um das dem Zugriffs-Edgedienst zugeordnete neue Zertifikat verwenden zu können. Ein ähnliches Verhalten tritt bei einem Benutzer in einer Webkonferenz mit dem Webkonferenz-Edgedienst auf. Das OAuthTokenIssuer-Zertifikat ist ein bestimmter Typ, der auf allen Servern freigegeben ist. Sie erstellen und verwalten das Zertifikat an einem Ort, und das Zertifikat wird im zentralen Verwaltungsspeicher für alle anderen Server gespeichert.



Zusätzliche Informationen werden benötigt, um die Optionen und Anforderungen bei der Verwendung des Set-CsCertificate-Cmdlet zum Bereitstellen von Zertifikaten vor dem Ablauf des aktuellen Zertifikats nachvollziehen zu können. Der Parameter "–Roll" ist wichtig, dient jedoch nur einem Zweck. Wenn Sie ihn als Parameter festlegen, informieren Sie damit "Set-CsCertificate", dass Sie Informationen zum betroffenen durch "–Type" definierten Zertifikat (z. B. AudioVideoAuthentication und OAuthTokenIssuer) bereitstellen werden, wenn das durch "–EffectiveDate" definierte Zertifikat gültig wird.

**-Roll:** Der Parameter "–Roll" ist erforderlich und besitzt Abhängigkeiten, die mit ihm bereitgestellt werden müssen. Parameter, die zum Festlegen der betroffenen Zertifikate und ihrer Anwendungsweise erforderlich sind:

**-EffectiveDate:** Der Parameter "–EffectiveDate" definiert, wann das neue Zertifikat zusammen mit dem aktuellen Zertifikat aktiv sein wird. "–EffectiveDate" kann nahe beim Ablaufdatum des aktuellen Zertifikats liegen oder ein längerer Zeitraum sein. Der empfohlene Mindestwert für "–EffectiveDate" für das AudioVideoAuthentication-Zertifikat ist acht Stunden. Dies ist die Standardgültigkeitsdauer des Tokens für AV-Edgediensttoken, die mithilfe des AudioVideoAuthentication-Zertifikats ausgestellt wurden.

Für das Bereitstellen der OAuthTokenIssuer-Zertifikate liegen verschiedene Anforderungen für die Durchlaufzeit vor, bevor das Zertifikat wirksam werden kann. Der Mindestwert des OAuthTokenIssuer-Zertifikats für die Durchlaufzeit sollte 24 Stunden vor der Ablaufzeit des aktuellen Zertifikats betragen. Die erweiterte Durchlaufzeit für die Koexistenz ist durch andere Serverrollen begründet, die von dem OAuthTokenIssuer-Zertifikat (beispielsweise Exchange Server) abhängen, das eine längere Aufbewahrungszeit für durch Zertifikate erstellte Authentifizierungs- und Verschlüsselungsschlüsselelemente besitzt.

**-Thumbprint:** Beim Fingerabdruck handelt es sich um ein für dieses Zertifikat eindeutiges Attribut. Mit dem Parameter "–Thumbprint" wir das Zertifikat ermittelt, das von den Aktionen des Cmdlets "Set-CsCertificate" betroffen ist.

**-Type:** Der Parameter "–Type" kann einen einzelnen Typ für die Zertifikatverwendung oder eine durch Komma getrennte Liste der Zertifikatverwendungstypen akzeptieren. Die Zertifikattypen geben für das Cmdlet und den Server an, worin der Zweck des Zertifikats besteht. Beispiel: Der Typ "AudioVideoAuthentication" ist für die Verwendung durch den A/V-Edgedienst und den AV-Authentifizierungsdienst vorgesehen. Wenn Sie verschiedene Zertifikattypen zum gleichen Zeitpunkt bereitstellen möchten, müssen Sie die längste effektive Mindestdurchlaufzeit für die Zertifikate berücksichtigen. Sie müssen beispielsweise Zertifikate vom Typ "AudioVideoAuthentication" und Typ "OAuthTokenIssuer" bereitstellen. Als Mindestwert muss für "–EffectiveDate" der höhere Wert der beiden Zertifikate festgelegt werden, in diesem Fall der Wert des Zertifikats "OAuthTokenIssuer", dessen Mindestdurchlaufzeit 24 Stunden beträgt. Wenn Sie das Zertifikat "AudioVideoAuthentication" nicht mit einer Durchlaufzeit von 24 Stunden bereitstellen möchten, stellen Sie es separat mit einem Ihren Anforderungen entsprechenden Wert für "EffectiveDate" bereit.

## So aktualisieren oder erneuern Sie ein A/V-Edgedienst-Zertifikat mit den Paramentern "–Roll" und "-EffectiveDate"

1.  Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2.  Fordern Sie eine Erneuerung oder ein neues AudioVideoAuthentication-Zertifikat mit exportierbarem privatem Schlüssel für das vorhandene Zertifikat für den A/V-Edgedienst an.

3.  Importieren Sie das neue AudioVideoAuthentication-Zertifikat auf dem Edgeserver und allen anderen Edgeservern in Ihrem Pool (sofern ein Pool bereitgestellt wurde).

4.  Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet "Set-CsCertificate", und verwenden Sie den Parameter "–Roll" mit dem Parameter "–EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden. Dadurch wird ein Zeitpunkt, zu dem das Zertifikat auf aktiv gesetzt werden muss, und damit ein Wert für "–EffectiveDate \<string\> festgelegt: “7/22/2012 6:00:00 AM”.
    

    > [!IMPORTANT]
    > Für einen Edgepool müssen alle AudioVideoAuthentication-Zertifikate nach Datum und Uhrzeit, das bzw. die durch den Parameter "–EffectiveDate" des ersten bereitgestellten Zertifikats angegeben wird, bereitgestellt sein, um eine mögliche A/V-Kommunikationsunterbrechung zu vermeiden, die durch das Ablaufen des älteren Zertifikats vor der Erneuerung aller Client- und Consumertoken mithilfe des neuen Zertifikats verursacht werden kann.

    
    Der Befehl "Set-CsCertificate" mit den Parametern "–Roll" und "–EffectiveTime":
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Ein Set-CsCertificate-Beispielbefehl:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    

    > [!IMPORTANT]
    > Das Gültigkeitsdatum muss so formatiert werden, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.



Mit einer optischen Zeitachse können Sie den besser verstehen, der von "Set-CsCertificate", "-Roll" und "–EffectiveDate" zum Bereitstellen eines neuen Zertifikats für die Aussstellung neuer AudioVideoAuthentication-Token verwendet wird, während weiterhin mit einem vorhandenen Zertifikat das von Benutzern verwendete AudioVideoAuthentication-Zertifikat validiert wird.

Im folgenden Beispiel legt der Administrator fest, dass das A/V-Edgedienst-Zertifikat am 22.07.2012 um 14 Uhr abläuft. Er fordert ein neues Zertifikat an, erhält es und importiert es auf jedem Edgeserver in seinem Pool. Am 22.07.2012 um 14 Uhr startet er die Ausführung von "Get-CsCertificate" mit "–Roll", "-Thumbprint" (dieser Wert entspricht der Fingerabdruckzeichenfolge des neuen Zertifikats) und "–EffectiveTime" (für diesen Wert ist 22.07.2012 6:00:00 Uhr festgelegt). Er führt diesen Befehl auf jedem Edgeserver aus.

![Verwenden der Parameter „Roll“ und „EffectiveDate“](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Verwenden der Parameter „Roll“ und „EffectiveDate“")

Wird das Gültigkeitsdatum (22.07.2012 6:00:00 Uhr) erreicht, werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2012 14:00:00 Uhr), werden Token nur durch das neue Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets "Remove-CsCertificate" mit dem Parameter "–Previous" sicher entfernt werden.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

## So aktualisieren oder erneuen Sie ein OAuthTokenIssuer-Zertifikat mit den Parametern "–Roll" und "-EffectiveDate"

1.  Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2.  Fordern Sie eine Erneuerung oder ein neues OAuthTokenIssuer-Zertifikat mit exportierbarem privatem Schlüssel für das vorhandene Zertifikat für den A/V-Edgedienst an.

3.  Importieren Sie das neue OAuthTokenIssuer-Zertifikat auf einem Front-End-Server in Ihrem Pool (sofern ein Pool bereitgestellt wurde). Das OAuthTokenIssuer-Zertifikat wird global repliziert und muss auf den Servern in Ihrer Bereitstellung aktualisiert und erneuert werden. Der Front-End-Server wird als Beispiel verwendet.

4.  Konfigurieren Sie das importierte Zertifikat mit dem Cmdlet "Set-CsCertificate", und verwenden Sie den Parameter "–Roll" mit dem Parameter "–EffectiveDate". Das Gültigkeitsdatum sollte als Ablaufzeit des aktuellen Zertifikats (14:00:00 Uhr) minus Tokengültigkeitsdauer (standardmäßig acht Stunden) festgelegt werden.
    
    Der Befehl "Set-CsCertificate" mit den Parametern "–Roll" und "–EffectiveTime":
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Ein Set-CsCertificate-Beispielbefehl:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    

    > [!IMPORTANT]
    > Das Gültigkeitsdatum muss so formatiert werden, dass es den Regions- und Spracheinstellungen Ihres Servers entspricht. Im Beispiel werden die englischen (USA) Regions- und Spracheinstellungen verwendet.



Wird das Gültigkeitsdatum (21.07.2012 01:00:00 Uhr) erreicht, werden alle neuen Token vom neuen Zertifikat ausgestellt. Bei der Validierung von Token werden die Token zunächst anhand des neuen Zertifikats überprüft. Schlägt die Überprüfung fehl, wird das alte Zertifikat verwendet. Die Vorgehensweise, erst das neue und anschließend das alte Zertifikat zu verwenden, wird bis zur Ablaufzeit des alten Zertifikats fortgesetzt. Sobald das alte Zertifikat abgelaufen ist (22.07.2012 14:00:00 Uhr), werden Token nur durch das neue Zertifikat überprüft. Das alte Zertifikat kann mithilfe des Cmdlets "Remove-CsCertificate" mit dem Parameter "–Previous" sicher entfernt werden.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

## Siehe auch

#### Konzepte

[Planen von Edgeserver-Zertifikaten in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  

#### Weitere Ressourcen

[Einrichten von Edgezertifikaten für Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)  
[Remove-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCertificate)

