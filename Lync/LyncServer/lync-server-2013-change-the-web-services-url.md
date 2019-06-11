---
title: 'Lync Server 2013: Ändern der Webdienste-URL'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335c73a56da1d8b9a28e7089a7cc2238724a322b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>Ändern der Webdienste-URL in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-11-16_

Wenn Sie Ihre Front-End-Pools und Standard Edition-Server einrichten, haben Sie die Möglichkeit, einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und zugeordnete Ports für eine externe Webfarm zu konfigurieren. Wenn Sie diese URL beim Ausführen des lync Server-Bereitstellungs-Assistenten nicht konfiguriert haben, müssen Sie diese Einstellungen manuell konfigurieren. Ein Administrator muss diese Einstellungen in der Regel nicht ändern, da es sich hierbei um die empfohlenen und Standardanschlüsse handelt.

<div>


> [!NOTE]  
> Der folgende Screenshot wurde beim Konfigurieren eines Standard Edition-Servers ausgeführt, sodass die Option "FQDN überschreiben" deaktiviert ist. Diese Option ist bei der Konfiguration eines Enterprise Edition-Servers in einem Front-End-Pool aktiviert.



</div>

![Bearbeiten von Webdienste-Pool Einstellungen] (images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Bearbeiten von Webdienste-Pool Einstellungen")

<div>

## <a name="to-configure-web-services"></a>So konfigurieren Sie Webdienste

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

3.  Wählen Sie im Topologie-Generator in der Konsolenstruktur unter **Standard Edition-Front-End-Server**, **Enterprise Edition-Front-End-Pools**und **Verzeichnis Pools**den Namen des Pools aus. Klicken Sie mit der rechten Maustaste auf den Namen, klicken Sie auf **** **Eigenschaften bearbeiten**, und klicken Sie dann auf Webdienste.

4.  Fügen Sie den **FQDN der externen**Webdienste hinzu, oder bearbeiten Sie ihn, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein. Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein.

    
    </div>

5.  Überprüfen Sie, ob die Überwachungs-und Veröffentlichungs Anschlüsse für Ihre Umgebung ordnungsgemäß konfiguriert sind.

6.  Wiederholen Sie diese Schritte für alle Standard Edition-Server, Front-End-Pools und Director-Pools in Ihrer Umgebung.

7.  Klicken Sie in der Konsolenstruktur auf **lync Server 2013**, und klicken Sie dann im Bereich **Aktionen** auf **Topologie veröffentlichen**.

Wenn Sie die Überwachungs-und Veröffentlichungs Anschlüsse konfigurieren möchten, müssen Sie einige Anforderungen berücksichtigen:

  - Die angezeigten Ports sind die Ports, die auf jedem Front-End-Server für Internet Information Server (IIS) konfiguriert sind.

  - Die internen und externen Überwachungsanschlüsse müssen für IIS unterschiedlich sein. Bei den externen Überwachungs Anschlüssen sind diese normalerweise identisch, da Sie den Hardwarelastenausgleich für den internen Webverkehr darstellen und einer der Reverse-Proxy Server für externen Webverkehr darstellt.

  - Sie können die internen Webdienste in einem Front-End-Pool, einem Director oder einem Director-Pool außer Kraft setzen und ihren eigenen FQDN definieren.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie sich entscheiden, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.

    
    </div>

  - Die veröffentlichten Ports müssen auf dem Reverse Proxy oder Hardware Load Balancer als Abhör Anschlüsse konfiguriert sein.

  - Bei einem Front-End-Pool (nicht im Beispiel dargestellt) muss sich der FQDN des internen SIP-Pools vom internen Webdienst-FQDN unterscheiden, da Webdatenverkehr über das Hardwarelastenausgleich-Modul erfolgt und der interne SIP-Pool-Datenverkehr über das DNS Load Balancer erfolgt. . Diese Anforderung muss erfüllt sein.

  - Eine lync Server Standard Edition-Bereitstellung muss nicht überschrieben werden, damit ein interner FQDN des Webdiensts nicht überschrieben werden kann, da dieser Server nicht Lastenausgleich erfolgen kann.

  - Wenn Sie in Ihrer Umgebung über ein Hardware-Lastenausgleichsmodul verfügen, das Sie sowohl für den internen SIP-als auch für den Webverkehr verwenden, kann der Topologie-Generator die Unterscheidung nicht durchführen.
    
    Webdienst-FQDNs sollten problemlos voneinander unterschieden werden. Dadurch wird sichergestellt, dass die URL-Umleitung Clients auf den entsprechenden Server verweist. Wenn Sie beispielsweise über zwei FQDNs verfügen, sollten Sie einen Meeting.contoso.com und den anderen Conferencing.contoso.com benennen. Wenn Sie FQDNs mit ähnlichen Namen wie "meet1.contoso.com" und "meet2.contoso.com" haben, können Sie möglicherweise zu Umleitungs Problemen führen.

Die externen Webdienste funktionieren in Verbindung mit einem Reverse-Proxy im Umkreisnetzwerk. Es bietet Clients externen Zugriff auf die Verwendung dieser Webdienste. Die hier konfigurierten FQDNs werden an Clients gesendet, wenn Sie sich anmelden, und werden verwendet, um eine HTTPS-Verbindung zurück zum Reverse-Proxy herzustellen, wenn eine Remoteverbindung hergestellt wird. Der Reverse-Proxy-Server leitet den FQDN des externen Webdiensts an ein internes Hardware-Lastenausgleichsmodul oder direkt an den Pool weiter. Der Reverse-Proxy muss den FQDN der externen Webdienste in die IP-Adresse des internen Webservers auflösen können. Die externen Webdienste-FDQN müssen im öffentlichen Internet aufgelöst werden können.

Wenn es sich bei dem internen Server um einen Standard Edition-Server handelt, handelt es sich bei dem internen FQDN um den FQDN des Standard Edition-Servers. Wenn es sich bei dem internen Server um einen Front-End-Pool handelt, handelt es sich bei dem FQDN um einen Hardware-Lastenausgleichsmodul (Virtual IP, VIP), mit dem die internen Webfarmserver ausgeglichen werden. Ein Hardware-Lastenausgleichsmodul ist in einem Front-End-Pool mit mehr als einem Enterprise Edition-Server erforderlich. Ein Lastenausgleichsmodul ist für einen Standard Edition-Server oder einen einzelnen Enterprise Edition-Front-End-Server nicht erforderlich.

</div>

</div>

<span> </span>

</div>

</div>

</div>

