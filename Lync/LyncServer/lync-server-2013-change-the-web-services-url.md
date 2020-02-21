---
title: 'Lync Server 2013: Ändern der Webdienste-URL'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94424edc38cf1cc0eacac2638a4ed30a18f06779
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>Ändern der Webdienste-URL in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-11-16_

Bei der Einrichtung von Front-End-Pools und Standard Edition-Servern können Sie einen externen Webfarm-FQDN sowie entsprechende Ports konfigurieren. Wenn Sie diese URL nicht konfiguriert haben, als Sie den lync Server-Bereitstellungs-Assistenten ausgeführt haben, müssen Sie diese Einstellungen manuell konfigurieren. Ein Administrator muss diese Einstellungen normalerweise nicht ändern, da bereits die empfohlenen Standardports eingerichtet sind.

<div>


> [!NOTE]  
> Beim Konfigurieren eines Standard Edition-Server wurde der folgende Screenshot ausgeführt, sodass die Option FQDN außer Kraft setzen deaktiviert ist. Diese Option ist aktiviert, wenn ein Enterprise Edition-Server in einem Front-End-Pool konfiguriert wird.



</div>

![Bearbeiten von Webdienste Pool Einstellungen](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Bearbeiten von Webdienste Pool Einstellungen")

<div>

## <a name="to-configure-web-services"></a>So konfigurieren Sie Webdienste

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

3.  Wählen Sie im Topologie-Generator in der Konsolenstruktur unter **Front-End-Server der Standard Edition**, **Enterprise Edition-Front-End-Pools**und **Verzeichnis Pools**den Namen des Pools aus. Klicken Sie mit der rechten Maustaste auf den Namen, dann auf **Eigenschaften bearbeiten** und schließlich auf **Webdienste**.

4.  Fügen Sie unter **Externer FQDN für Webdienste** den FQDN hinzu bzw. bearbeiten Sie ihn, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server der FQDN der externen Webdienste eindeutig sein muss. Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für eine andere Front-End-Pool oder Front-End-Server verwenden. Wenn Sie auch Directors bereitstellen, muss der FQDN für externe Webdienste, der für einen Director-oder Directorpool definiert ist, von einem anderen Director oder Directorpool sowie von Front-End-Pool oder Front-End-Server eindeutig sein.

    
    </div>

5.  Stellen Sie sicher, dass die Überwachungs- und veröffentlichten Ports für Ihre Umgebung korrekt konfiguriert sind.

6.  Wiederholen Sie diese Schritte für alle Standard Edition-Server, Front-End-Pools und Director-Pools in Ihrer Umgebung.

7.  Klicken Sie in der Konsolenstruktur auf **Lync Server 2013**, und klicken Sie anschließend im Bereich **Aktionen** auf **Topologie veröffentlichen**.

Bei der Konfiguration der Überwachungs- und veröffentlichten Ports sollten Sie folgende Anforderungen beachten:

  - Die angezeigten Überwachungsports entsprechen den Ports, die für die Internetinformationsdienste (Internet Information Services, IIS) auf jedem Front-End-Server konfiguriert sind.

  - Der interne und der externe Überwachungsport müssen für IIS unterschiedlich lauten. Bei den externen Überwachungsports stimmen diese in der Regel überein, da ein Port das Hardwaregerät zum Lastenausgleich für den internen Webdatenverkehr und ein Port den Reverseproxyserver für den externen Webdatenverkehr repräsentiert.

  - Sie können die internen Webdienste auf einer Front-End-Pool, einem Director oder einem Directorpool außer Kraft setzen und ihren eigenen FQDN definieren.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.

    
    </div>

  - Die veröffentlichten Ports müssen auf dem Reverseproxy oder auf dem Hardwaregerät zum Lastenausgleich als Überwachungsports konfiguriert werden.

  - Für einen Front-End-Pool (nicht im Beispiel gezeigt) muss sich der interne FQDN für den SIP-Pool von dem internen FQDN der Webdienste unterscheiden, da der Webdatenverkehr über das Hardwaregerät zum Lastenausgleich und der interne Datenverkehr des SIP-Pools über den DNS-Lastenausgleich verläuft. Diese Anforderung muss erfüllt werden.

  - Bei einer lync Server Standard Edition-Bereitstellung muss kein interner FQDN für Webdienste außer Kraft gesetzt werden, da dieser Server nicht Lastenausgleich sein kann.

  - Wenn in Ihrer Umgebung ein Hardwaregerät zum Lastenausgleich vorhanden ist, das Sie sowohl für den internen als auch für den Webdatenverkehr verwenden, kann der Topologie-Generator diese Unterscheidung nicht vornehmen.
    
    Webdienst-FQDNs sollten leicht voneinander unterschieden werden; Dadurch wird sichergestellt, dass die URL-Umleitung Clients auf den entsprechenden Server verweist. Wenn Sie beispielsweise zwei FQDNs haben, sollten Sie eine Meeting.contoso.com und die andere Conferencing.contoso.com benennen. Möglicherweise treten Umleitungs Probleme auf, wenn Sie FQDNs mit ähnlicheren Namen wie meet1.contoso.com und meet2.contoso.com haben.

Die externen Webdienste funktionieren zusammen mit einem Reverseproxy im Umkreisnetzwerk. Es stellt Clients externen Zugriff auf mithilfe dieser Webdienste bereit. Die an dieser Stelle konfigurierten FQDNs werden an Clients gesendet, wenn diese sich anmelden, und sie werden bei einer Remoteverbindung zum Herstellen einer HTTPS-Verbindung zurück zum Reverseproxy eingesetzt. Der Reverseproxyserver leitet den FQDN für den externen Webdienst an ein internes Hardwaregerät zum Lastenausgleich oder direkt an den Pool weiter. Der Reverseproxy muss in der Lage sein, den externen FQDN für die Webdienste in die IP-Adresse des internen Webservers aufzulösen. Der FQDN für externe Webdienste muss im öffentlichen Internet auflösbar sein.

Wenn es sich bei dem internen Server um einen Standard Edition-Server handelt, handelt es sich bei dem internen FQDN um den Standard Edition-Server-FQDN. Handelt es sich bei Ihrem internen Server um einen Front-End-Pool, entspricht der FQDN einer virtuellen IP (VIP) für das Hardwaregerät zum Lastenausgleich, das den Lastenausgleich für die internen Webfarmserver durchführt. Ein Hardwaregerät zum Lastenausgleich ist in einem Front-End-Pool mit mehreren Enterprise Edition-Servern erforderlich. Für einen Standard Edition-Server oder einen einzelnen Front-End-Server der Enterprise Edition ist kein Lastenausgleichssystem erforderlich.

</div>

</div>

<span> </span>

</div>

</div>

</div>

