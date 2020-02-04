---
title: 'Lync Server 2013: Komponenten und Topologien für Konferenzen'
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
ms.openlocfilehash: db44e7c8430865fcf8138c9b51f6e700ff85dd7b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Komponenten und Topologien für Konferenzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-04_

Wenn Sie im Topologie-Generator Konferenzen auswählen, wird Conferencing als Teil des Front-End-Servers oder Standard Edition-Servers bereitgestellt. Für Einwahlkonferenzen und PowerPoint-Freigabe sind zusätzliche Komponenten und Konfiguration erforderlich. In den folgenden Abschnitten werden die unterstützten Komponenten und Topologien für Webkonferenzen, A/V-Konferenzen und Einwahlkonferenzen beschrieben.

<div>

## <a name="supported-components"></a>Unterstützte Komponenten

Die einzigen Komponenten Webkonferenzen und A/V-Konferenzen erfordern die Front-End-Server Ihrer Organisation oder Standard Edition-Server. Eine Liste der Hardware-und Softwareanforderungen für die Front-End-Server und die Standard Edition-Server finden Sie unter [Unterstützte Hardware für lync Server 2013](lync-server-2013-supported-hardware.md) und [Server Software und Infrastrukturunterstützung in lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

In lync Server 2013 werden Office Web Apps und der Office Web Apps-Server verwendet, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu verarbeiten. Details zum Installieren und Konfigurieren des Office Web Apps-Servers finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Zusätzlich zu den Anforderungen für Webkonferenzen und A/V-Konferenzen verwendet Einwahlkonferenzen die folgenden lync Server 2013-Komponenten:

  - **Application Service**   Application Service stellt eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen (UC) bereit. Einwahlkonferenzen verwendet zwei UC-Anwendungen, die Anwendungsdienst erfordern: Konferenzzentrale und Konferenzankündigung. Der Anwendungsdienst wird standardmäßig auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server installiert und aktiviert, wenn Sie eine Konferenz Arbeitsauslastung bereitstellen und die Option für Einwahlkonferenzen auswählen.

  - ****   Die Application Conferencing Attendant-Anwendung der Konferenzzentrale ist eine Unified Communications-Anwendung, die PSTN-Anrufe (Public Switched Telephone Network) akzeptiert, Aufforderungen wiedergibt und die Anrufe an eine a/V-Konferenz anschließt. Die Conferencing Attendant-Anwendung wird standardmäßig installiert und aktiviert, wenn Sie eine Konferenz Arbeitsauslastung bereitstellen und die Option für Einwahlkonferenzen auswählen.

  - **Konferenzankündigung**   Application Conferencing Ankündigung Application ist eine Unified Communications-Anwendung, die in bestimmten Aktionen Töne und Aufforderungen an PSTN-Teilnehmer abspielt, beispielsweise wenn Teilnehmer an einer Konferenz teilnehmen oder eine Konferenz abhalten, Teilnehmer stumm geschaltet oder nicht stumm geschaltet werden, jemand in die Konferenz Lobby wechselt oder die Konferenz gesperrt oder gesperrt ist. Die APP für Konferenz Ankündigungen unterstützt auch DTMF-Befehle (Dual Tone MultiFrequency) über das Tastenfeld des Telefons. Die APP für Konferenz Ankündigungen wird automatisch installiert und aktiviert, wenn Sie eine Konferenz Arbeitsauslastung bereitstellen und die Option für Einwahlkonferenzen auswählen.

  - **Seite "Einstellungen für Einwahlkonferenzen**   " auf der Seite "Einstellungen für Einwahlkonferenzen" werden Konferenzeinwahl Nummern mit den verfügbaren Sprachen, zugewiesene Konferenz Informationen (für Besprechungen, die nicht geplant werden müssen) sowie DTMF-Steuerelemente in der Konferenz und unterstützt die Verwaltung von PIN (Personal Identification Number) sowie zugewiesene Konferenz Informationen angezeigt. Die Seite Einstellungen für Einwahlkonferenzen wird automatisch als Teil von Webdiensten installiert.

  - **Für lync Server 2013, Vermittlungsserver und**   Einwahlkonferenzen für PSTN-Gateways ist ein Vermittlungsserver erforderlich, um Signalisierungen (und Medien in einigen Konfigurationen) zwischen lync Server 2013 und dem PSTN-Gateway zu übersetzen, und ein PSTN-Gateway, um Signalisierungs-und Medien Verbindungen zwischen dem Vermittlungsserver und dem PSTN-Gateway zu übersetzen. Für Einwahlkonferenzen müssen Sie mindestens einen Vermittlungs Server und mindestens eine der folgenden Aktionen bereitstellen:
    
      - PSTN-Gateway
    
      - IP-Nebenstellenanlage
    
      - Session Border Controller (SBC) (für einen Anbieter von Internettelefoniediensten, mit dem durch Konfigurieren eines SIP-Trunks eine Verbindung hergestellt wird)
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie auch Enterprise-VoIP bereitstellen, sind Vermittlungs Server und PSTN-Gateways Teil der Enterprise-VoIP-Bereitstellung. Wenn Sie Enterprise-VoIP nicht bereitstellen, müssen Sie mindestens einen Vermittlungs Server und mindestens ein PSTN-Gateway, IP-PBX oder SBC für Einwahlkonferenzen bereitstellen.

    
    </div>

  - **Datei**   Speicherdatei Speicher wird für aufgezeichnete Namen-Audiodateien verwendet. Er ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.

  - **Benutzerspeicher Benutzerspeicher**wird zum Speichern von Benutzer-lync Server 2013-Pins verwendet.    Für PINs wird ein Hashalgorithmus verwendet. Der Benutzerspeicher ist eine Standardkomponente in jeder Enterprise Edition- oder Standard Edition-Bereitstellung.

  - **Lync Server Control Panel**   einige Einwahleinstellungen können mithilfe der lync Server-Systemsteuerung konfiguriert werden.

  - **Lync Server-Verwaltungsshell**   alle Einwahleinstellungen können mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden. Cmdlets für die lync Server-Verwaltungsshell sind für das bereitstellen, konfigurieren, ausführen, überwachen und behandeln von Problemen mit der Anwendungs-und Konferenz ansageanwendung für Conferencing Attendant verfügbar. Details zu bestimmten Cmdlets finden Sie unter Dokumentation zur lync Server-Verwaltungsshell.

</div>

<div>

## <a name="supported-topologies"></a>Unterstützte Topologien

In lync Server 2013 ist der Server, auf dem Konferenzdienste ausgeführt werden, immer mit den Front-End-Servern oder Standard Edition-Servern verbunden. Während der ersten Bereitstellung bietet Ihnen der Topology Builder die Möglichkeit, Konferenzen in Ihre Topologie einzubeziehen. Den Topologie-Generator können Sie außerdem nutzen, um die Konferenzfunktion zu einer vorhandenen Bereitstellung hinzuzufügen. Ausführliche Informationen finden Sie unter [definieren und Konfigurieren der Topologie in lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

<div>

## <a name="dial-in-conferencing-toplogies"></a>Einwahl in Konferenz Toplogies

Sie können Einwahlkonferenzen in den folgenden Topologien und Konfigurationen bereitstellen:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Mit oder ohne Enterprise Voice

Sie können Anwendungsdienst, Konferenz Aufsichts Anwendung und Konferenz Ankündigungs Anwendung an einer zentralen Website, aber nicht an einer Zweigstelle bereitstellen.

<div>


> [!NOTE]  
> Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie Sie in jedem Pool bereitstellen, in dem Sie die lync Server 2013-Konferenz bereitstellen. Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen, aber Sie müssen die Funktion für Einwahlkonferenzen in jedem Pool bereitstellen. Diese Anforderung unterstützt das Feature "aufgezeichnete Namen", wenn ein Benutzer eine Zugriffsnummer aus einem Pool anruft, um an einer lync Server 2013-Konferenz in einem anderen Pool teilzunehmen.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Unterstützte Topologien für lync Server 2013 und Office Web Apps

Lync Server 2013 bietet die folgenden Möglichkeiten zum Konfigurieren von Office Web Apps Server. Je nach Ihren Anforderungen können Sie:

  - **Installieren Sie lync Server 2013 und Office Web Apps Server lokal hinter der Firewall Ihrer Organisation und in derselben Netzwerkzone.** Bei dieser Topologie wird externer Zugriff auf Office Web Apps Server über den Reverse-Proxy Server bereitgestellt. Sowohl lync Server 2013 als auch Office Web Apps Server (oder eine Office Web Apps-Serverfarm) sind lokal und hinter der Firewall Ihrer Organisation installiert. Im Idealfall sollten Sie Office Web Apps Server in der gleichen Netzwerkzone wie lync Server installieren.
    
    Externe lync-Clients können mithilfe eines Reverseproxy-Servers, der Anforderungen aus dem Internet anfordert und an das interne Netzwerk weiterleitet, eine Verbindung mit lync Server 2013 und Office Web Apps Server herstellen. (Interne Clients müssen den Reverse Proxy Server nicht verwenden, da Sie eine direkte Verbindung mit Office Web Apps Server herstellen können.) Diese Topologie funktioniert am besten, wenn Sie eine dedizierte Office Web Apps-Server Farm verwenden möchten, die nur von lync Server 2013 verwendet wird.

  - **Verwenden eines extern bereitgestellten Office Web Apps-Servers**
    
    In dieser Topologie wird lync Server 2013 lokal bereitgestellt und verwendet einen Office Web Apps-Server, der außerhalb der lync Server-Netzwerkzone bereitgestellt wird. Dies kann passieren, wenn der Office Web Apps-Server für mehrere Anwendungen im Unternehmen freigegeben und in einem Netzwerk bereitgestellt wird, in dem lync Server für die Verwendung der externen Schnittstelle von Office Web Apps Server und umgekehrt erforderlich ist.
    
    Sie müssen keinen Reverse-Proxy-Server installieren; Stattdessen werden alle Anforderungen vom Office Web Apps-Server an lync Server 2013 über Ihren Edgeserver weitergeleitet. Sowohl Ihre internen als auch Ihre externen lync-Clients stellen mithilfe der externen URL eine Verbindung mit Office Web Apps Server her.
    
    Wenn der Office Web Apps-Server außerhalb ihrer internen Firewall bereitgestellt wird, wählen Sie die Option **Office Web Apps Server wird in einem externen Netzwerk (also Umkreis/Internet) im Topologie-Generator bereitgestellt** . Weitere Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Unabhängig von der ausgewählten Topologie ist es entscheidend, dass die korrekten Firewallports geöffnet sind. Sie müssen sicherstellen, dass DNS-Namen, IP-Adressen und Ports nicht von Firewalls auf dem Office Web Apps-Server, dem Lastenausgleichsmodul oder lync Server blockiert werden.

<div>


> [!NOTE]  
> Eine weitere Option für den externen Zugriff auf Office Web Apps Server ist die Bereitstellung des Servers im Umkreisnetzwerk. Wenn Sie sich dafür entscheiden, sollten Sie Bedenken, dass der Server Computer von Office Web Apps Server als Mitglied Ihrer Active Directory-Domäne verwendet werden muss. Sofern Ihre Netzwerkrichtlinie Computern im Umkreisnetzwerk keine Active Directory-Domänenmitglieder zulässt, wird empfohlen, dass Sie Office Web Apps Server im Umkreisnetzwerk nicht installieren. Stattdessen sollten Sie Office Web Apps Server im internen Netzwerk installieren und den Zugriff externer Benutzer über den Reverse-Proxy Server bereitstellen.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

