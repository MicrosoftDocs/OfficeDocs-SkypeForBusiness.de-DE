---
title: Lync Server 2013 Komponenten und Topologien für Konferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d14c12ad1e28dc2a40fed5b19b5928a5bedc069
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Komponenten und Topologien für Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-04_

Wenn Sie im Topologie-Generator Konferenzen auswählen, wird die Konferenz im Rahmen der Front-End-Server oder Standard Edition-Server bereitgestellt. Für Einwahlkonferenzen und PowerPoint-Freigabe sind zusätzliche Komponenten und Konfigurationen erforderlich. In den folgenden Abschnitten werden die unterstützten Komponenten und Topologien für Webkonferenzen, A/V-Konferenzen und Einwahlkonferenzen beschrieben.

<div>

## <a name="supported-components"></a>Unterstützte Komponenten

Die einzigen Komponenten, die Webkonferenzen und A/V-Konferenzen erfordern, sind die Front-End-Server Ihrer Organisation oder Standard Edition-Server. Eine Liste der Hardware-und Softwareanforderungen für die Front-End-Server und Standard Edition-Server finden Sie unter [Supported Hardware for lync Server 2013](lync-server-2013-supported-hardware.md) and [Server Software and Infrastructure Support in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

Lync Server 2013 verwendet Office-Webanwendungen und den Office-webapps-Server, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu verarbeiten. Ausführliche Informationen zum Installieren und Konfigurieren des Office-webapps-Servers finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Zusätzlich zu den Anforderungen für Webkonferenzen und A/V-Konferenzen verwendet Einwahlkonferenzen die folgenden lync Server 2013 Komponenten:

  - **Anwendungsdienst**   Anwendungsdienst stellt eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen (UC) bereit. Bei Einwahlkonferenzen werden zwei UC-Anwendungen verwendet, die Anwendungsdienst erfordern: Konferenzzentrale und Konferenz Ansage. Anwendungsdienst wird bei jedem Front-End-Server in einem Front-End-Pool und auf jeder Standard Edition-Server standardmäßig installiert und aktiviert, wenn Sie eine Konferenz Arbeitsauslastung bereitstellen und die Option "Einwahlkonferenzen" auswählen.

  - **Konferenzzentrale**   Konferenzzentrale ist eine Unified Communications-Anwendung, die PSTN-Anrufe (Public Switched Telephone Network) akzeptiert, Ansagen abgibt und die Anrufe an eine a/V-Konferenz anschließt. Konferenzzentrale wird standardmäßig installiert und aktiviert, wenn Sie eine Konferenz Arbeitsauslastung bereitstellen und die Option "Einwahlkonferenzen" auswählen.

  - **Konferenzankündigungsanwendung**   Konferenzankündigungsanwendung ist eine Unified Communications-Anwendung, die für bestimmte Aktionen Töne und Ansagen an PSTN-Teilnehmer abgibt, beispielsweise wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, die Teilnehmer stumm geschaltet oder stumm geschaltet werden, jemand in die Konferenz Lobby wechselt oder die Konferenz gesperrt oder entsperrt ist. Konferenzankündigungsanwendung unterstützt auch DTMF-Befehle (Dual-Tone MultiFrequency) über die Telefontastatur. Konferenzankündigungsanwendung wird automatisch installiert und standardmäßig aktiviert, wenn Sie eine Konferenz Arbeitsauslastung bereitstellen und die Option Einwahlkonferenzen auswählen.

  - **Seite "Einstellungen für Einwahlkonferenzen"**   das Seite "Einstellungen für Einwahlkonferenzen" zeigt Konferenzeinwahl Nummern mit den verfügbaren Sprachen an, zugewiesene Konferenz Informationen (also für Besprechungen, die nicht geplant werden müssen) sowie DTMF-Steuerelemente in der Konferenz und unterstützt die Verwaltung von persönlicher Identifikationsnummer (PIN) und zugewiesener Konferenz Informationen. Das Seite "Einstellungen für Einwahlkonferenzen" wird automatisch als Teil von Webdienste installiert.

  - **Für lync Server 2013-, Vermittlungsserver-und PSTN-Gateway**   -Einwahlkonferenzen ist ein Vermittlungsserver erforderlich, um Signalübertragungen (und Medien in einigen Konfigurationen) zwischen lync Server 2013 und dem PSTN-Gateway und ein PSTN-Gateway zu übersetzen, um Signal-und Medienübertragung zwischen dem Vermittlungsserver und dem PSTN-Gateway zu übersetzen. Bei Einwahlkonferenzen müssen Sie mindestens eine Vermittlungsserver und mindestens eine der folgenden bereitstellen:
    
      - PSTN-Gateway
    
      - IP-Nebenstellenanlage
    
      - Session Border Controller (SBC) (für einen Internet Telefonie-Dienstanbieter, zu dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren)
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie auch Enterprise-VoIP bereitstellen, sind Vermittlungsserver-und PSTN-Gateways Teil der Enterprise-VoIP-Bereitstellung. Wenn Sie Enterprise-VoIP nicht bereitstellen, müssen Sie mindestens eine Vermittlungsserver und mindestens ein PSTN-Gateway, eine IP-PBX-Anlage oder einen SBC für Einwahlkonferenzen bereitstellen.

    
    </div>

  - **Dateispeicher**   Dateispeicher wird für aufgezeichnete Namen-Audiodateien verwendet. Dateispeicher ist eine Standardkomponente in jeder Enterprise Edition-oder Standard Edition-Bereitstellung.

  - **User Store User**Store dient zum Speichern von Benutzer lync Server 2013 Pins.    Pins werden gehasht. Der Benutzerspeicher ist eine Standardkomponente in jeder Enterprise Edition-oder Standard Edition-Bereitstellung.

  - **Lync Server-Systemsteuerung**   einige Einwahleinstellungen können mithilfe von lync Server-Systemsteuerung konfiguriert werden.

  - **Lync Server-Verwaltungsshell**   alle Einwahleinstellungen können mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden. Lync Server-Verwaltungsshell-Cmdlets stehen für die Bereitstellung, Konfiguration, Ausführung, Überwachung und Problembehandlung von Konferenzzentrale und Konferenzankündigungsanwendung zur Verfügung. Ausführliche Informationen zu bestimmten Cmdlets finden Sie unter lync Server-Verwaltungsshell Dokumentation.

</div>

<div>

## <a name="supported-topologies"></a>Unterstützte Topologien

In lync Server 2013 ist der Server, auf dem die Konferenzdienste ausgeführt werden, immer mit den Front-End-Servern oder Standard Edition-Servern verbunden. Bei der anfänglichen Bereitstellung bietet der Topologie-Generator die Möglichkeit, Konferenzen in Ihre Topologie einzubeziehen. Sie können auch den Topologie-Generator verwenden, um einer vorhandenen Bereitstellung Konferenzen hinzuzufügen. Ausführliche Informationen finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

<div>

## <a name="dial-in-conferencing-toplogies"></a>Einwahl in Konferenz Konferenzen

Sie können Einwahlkonferenzen in den folgenden Topologien und Konfigurationen bereitstellen:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Mit oder ohne Enterprise-VoIP

Sie können Anwendungsdienst, Konferenzzentrale und Konferenzankündigungsanwendung an einem zentralen Standort bereitstellen, jedoch nicht an einem Zweigstellenstandort.

<div>


> [!NOTE]  
> Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie Sie in jedem Pool bereitstellen, in dem Sie lync Server 2013 Konferenzen bereitstellen. Sie müssen in keinem Pool Zugriffsnummern zuweisen, aber Sie müssen das Feature für Einwahlkonferenzen in jedem Pool bereitstellen. Diese Anforderung unterstützt das Feature für aufgezeichnete Namen, wenn ein Benutzer eine Zugriffsnummer aus einem Pool aufruft, um an einer lync Server 2013 Konferenz in einem anderen Pool teilzunehmen.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Unterstützte Topologien für lync Server 2013-und Office-Webanwendungen

Lync Server 2013 bietet die folgenden Möglichkeiten zum Konfigurieren von Office-webapps Server. Je nach Ihren Anforderungen können Sie Folgendes tun:

  - **Installieren Sie sowohl lync Server 2013 als auch Office-webapps-Server lokal hinter der Firewall Ihrer Organisation und in derselben Netzwerkzone.** Mit dieser Topologie wird der externe Zugriff auf Office-webapps Server über den Reverseproxy bereitgestellt. Sowohl lync Server 2013 als auch Office-webapps Server (oder eine Office-webapps-Serverfarm) werden lokal und hinter der Firewall Ihrer Organisation installiert. Im Idealfall sollten Sie Office-webapps-Server in derselben Netzwerkzone installieren wie lync Server.
    
    Externe lync-Clients können eine Verbindung mit lync Server 2013 und mit Office Web Apps Server herstellen, indem Sie einen Reverseproxy verwenden, bei dem es sich um einen Server handelt, der Anforderungen aus dem Internet aufnimmt und an das interne Netzwerk weiterleitet. (Interne Clients müssen nicht den Reverseproxy verwenden, da Sie direkt eine Verbindung mit Office-webapps Server herstellen können.) Diese Topologie eignet sich am besten, wenn Sie eine dedizierte Office-webapps-Server Farm verwenden möchten, die nur von lync Server 2013 verwendet wird.

  - **Verwenden eines extern bereitgestellten Office-webapps-Servers**
    
    In dieser Topologie wird lync Server 2013 lokal bereitgestellt und verwendet einen Office-webapps-Server, der außerhalb lync Server Netzwerkzone bereitgestellt wird. Dies kann vorkommen, wenn Office-webapps-Server für mehrere Anwendungen in der Corporation freigegeben wird und in einem Netzwerk bereitgestellt wird, das lync Server benötigt, um die externe Schnittstelle von Office-webapps Server zu verwenden und umgekehrt.
    
    Sie müssen keinen Reverse-Proxy Server installieren; Stattdessen werden alle Anforderungen vom Office-webapps-Server an lync Server 2013 über Ihren Edgeserver weitergeleitet. Sowohl Ihre internen als auch Ihre externen lync-Clients stellen über die externe URL eine Verbindung mit Office-webapps Server her.
    
    Wenn der Office Web Apps-Server außerhalb ihrer internen Firewall bereitgestellt wird, wählen Sie die Option **Office Web Apps Server wird in einem externen Netzwerk (d. Umkreis/Internet)** im Topologie-Generator bereitgestellt. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Unabhängig von der ausgewählten Topologie ist es wichtig, dass die richtigen Firewall-Ports geöffnet werden. Sie müssen sicherstellen, dass DNS-Namen, IP-Adressen und Ports nicht von Firewalls auf dem Office-webapps-Server, dem Lastenausgleichsmodul oder lync Server blockiert werden.

<div>


> [!NOTE]  
> Eine weitere Option für die Bereitstellung von externem Zugriff auf Office-webapps Server ist die Bereitstellung des Servers im Umkreisnetzwerk. Wenn Sie sich dafür entscheiden, müssen Sie beachten, dass der Server Computer für das Office-webapps-Server Setup Mitglied Ihrer Active Directory Domäne sein muss. Es wird empfohlen, dass Sie Office-webapps-Server nicht im Umkreisnetzwerk installieren, es sei denn, Ihre Netzwerkrichtlinie ermöglicht es Computern im Umkreisnetzwerk, Active Directory Domänenmitgliedern zu sein. Stattdessen sollten Sie Office-webapps-Server im internen Netzwerk installieren und externen Benutzern Zugriff über Ihren Reverse-Proxy Server bereitstellen.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

