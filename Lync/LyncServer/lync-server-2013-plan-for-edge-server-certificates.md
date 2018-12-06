---
title: 'Lync Server 2013: Planen von Edgeserver-Zertifikaten'
TOCTitle: Planen von Edgeserver-Zertifikaten
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413010(v=OCS.15)
ms:contentKeyID: 49295871
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen von Edgeserver-Zertifikaten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-05_

Die Erstellung von Zertifikaten für Edgeserver wurde in Lync Server 2013 vereinfacht.

**Zertifikatflussdiagramm für Edgeserver**

![Flussdiagramm zu Zertifikaten](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "Flussdiagramm zu Zertifikaten")

Erstellen Sie ein einzelnes öffentliches Zertifikat, stellen Sie sicher, dass ein exportierbarer privater Schlüssel für das Zertifikat definiert ist, und weisen Sie es unter Verwendung des Zertifikat-Assistenten den folgenden externen Edgeserverschnittstellen zu:


> [!IMPORTANT]
> Platzhalterzertifkate werden in Lync Server nicht unterstützt, es sein denn, sie werden zum Zusammenfassen der einfachen URLs über den Reverseproxy verwendet. Sie müssen für alle in Ihrer Bereitstellung angebotenen SIP-Domänennamen, Webkonferenz-Edgedienste, A/V-Edgedienste und XMPP-Domänen einen eindeutigen alternativen Antragstellernamen (SAN) definieren.




> [!NOTE]
> Das mit Lync Server 2013 eingeführte Bereitstellen von Audio/Video-Authentifizierungszertifikaten vor der Ablaufzeit des aktuellen Zertifikats erfordert einige zusätzliche Planungsschritte. Statt nur ein Zertifikat mit mehreren Zwecken für die externe Edgeschnittstelle brauchen Sie jetzt zwei Zertifikate: eines, das dem Zugriffs-Edgedienst und dem Webkonferenz-Edgedienst zugewiesen ist, und eines für den A/V-Edgedienst. Zusätzliche Informationen finden Sie unter <A href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate">Bereitstellen von AV- und OAuth-Zertifikaten in Lync Server 2013 mithilfe von -Roll in Set-CsCertificate</A>




> [!IMPORTANT]
> Im Falle eines Pools von Edgeservern exportieren Sie das Zertifikat mit dem privaten Schlüssel auf jeden Edgeserver und weisen das Zertifikat jedem Edgeserver-Dienst zu. Führen Sie die gleichen Schritte für das Zertifikat für den internen Edgeserver durch, wobei Sie das Zertifikat mit dem privaten Schlüssel exportieren und jeder internen Edgeschnittstelle zuweisen.



  - Stellen Sie sicher, dass ein exportierbarer privater Schlüssel für das Zertifikat zugewiesen ist.

  - Zugriffs-Edgedienst (im Zertifikat-Assistenten als **Externer SIP-Zugriffs-Edge** bezeichnet)

  - Webkonferenz-Edgedienst (im Zertifikat-Assistenten als **Externer Webkonferenz-Edge** bezeichnet)

  - Audio-Video-Authentifizierungsdienst (im Zertifikat-Assistenten als **Externer A/V-Edge** bezeichnet)

Erstellen Sie ein einzelnes internes Zertifikat mit exportierbarem privaten Schlüssel, kopieren Sie es und weisen Sie es jeder der folgenden internen Edgeserverschnittstellen zu:

  - Edgeserver (im Zertifikat-Assistenten als **Interner Edge** bezeichnet)


> [!IMPORTANT]
> Es besteht die Möglichkeit, für jeden Edgeserver-Dienst separate und eigene Zertifikate zu verwenden. Das ist besonders dann sinnvoll, wenn Sie das neue Feature für rollierende Zertifikate für das A/V-Edgedienst-Zertifikat verwenden möchten. Bei diesem Feature wird das Entkoppeln des A/V-Edgedienst-Zertifikats vom Zugriffs-Edgedienst und vom Webkonferenz-Edgedienst empfohlen. Wenn Sie festlegen, dass für jeden Dienst ein separates Zertifikat angefordert, bezogen und zugewiesen wird, müssen Sie anfordern, dass der private Schlüssel für den A/V-Edgedienst exportierbar ist (das ist tatsächlich der A/V-Authentifizierungsdienst) und der externen A/V-Edgeschnittstelle auf jedem Edgeserver das gleiche Zertifikat zuweisen.



## Siehe auch

#### Aufgaben

[Bereitstellen von AV- und OAuth-Zertifikaten in Lync Server 2013 mithilfe von -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)  

#### Konzepte

[Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

