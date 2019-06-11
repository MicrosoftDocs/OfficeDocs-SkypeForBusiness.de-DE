---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für zulässige externe Domänen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfab1a41f39d975d2920bdf97ea601618277f35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Wenn Sie die Unterstützung für Federated-Partner konfiguriert haben, können Sie verwalten, welche bestimmten Domänen mit Ihrer Organisation verbunden werden können. Sie konfigurieren eine oder mehrere bestimmte externe Domänen als zugelassene Verbunddomänen. Fügen Sie dazu jede Domäne zur Liste der zulässigen Domänen hinzu. Auch wenn die Partner Ermittlung für Ihre Organisation aktiviert ist, gehen Sie wie folgt vor, wenn es sich bei der Domäne um einen Verbundpartner handelt, der möglicherweise mit mehr als 1.000 ihrer Benutzer kommunizieren muss, oder wenn Sie möglicherweise mehr als 20 Nachrichten pro Sekunde senden müssen. Wenn die Partner Ermittlung für Ihre Organisation nicht aktiviert ist, können nur Benutzer externer Domänen, die Sie der Liste zugelassene Domänen hinzufügen, an Chats und Konferenzen mit Benutzern in Ihrer Organisation teilnehmen. Wenn Sie den Zugriff auf eine Verbunddomäne auf einen bestimmten Server einschränken möchten, auf dem der Access-Edgedienst des Verbundpartners ausgeführt wird, können Sie den Domänennamen des Servers angeben, auf dem der Access Edge-Dienst für jede Domäne in der Liste der zulässigen Domänen ausgeführt wird.

<div>


> [!NOTE]  
> In diesem Verfahren wird beschrieben, wie Sie die Unterstützung für bestimmte Domänen konfigurieren, aber die Implementierung der Unterstützung für verbundene Benutzer erfordert auch, dass Sie die Unterstützung für verbundene Benutzer für Ihre Organisation aktivieren und Richtlinien konfigurieren und anwenden, um zu steuern, welche Benutzer Zusammenarbeit mit Verbundbenutzern. Details zum Aktivieren der Unterstützung für Verbundbenutzer finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A>. Details zum Konfigurieren von Richtlinien für die Steuerung der Föderation finden Sie unter <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013</A>.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>So fügen Sie eine externe Domäne zur Liste der zulässigen Domänen hinzu

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie dann auf **Föderationsdomänen**.

4.  Klicken Sie auf der Seite **Federated Domains** auf **neu**und dann auf **zugelassene Domäne**.

5.  Führen Sie in **neuen Föderationsdomänen**die folgenden Aktionen aus:
    
      - Geben Sie in **Domänenname (oder FQDN)** den Namen der Föderationspartner-Domäne ein.
        
        <div>
        

        > [!NOTE]  
        > Dieser Name muss eindeutig sein und kann nicht bereits als zulässige Domäne für diesen Server mit dem Access Edge-Dienst vorhanden sein. Der Name darf nicht mehr als 256 Zeichen lang sein.<BR>Bei der Suche nach dem Domänennamen des Partner Partners wird eine Übereinstimmung mit dem Suffix ausgeführt. Wenn Sie beispielsweise <STRONG>contoso.com</STRONG>eingeben, gibt die Suche auch die Domäne <STRONG>IT.contoso.com</STRONG>zurück.<BR>Eine Föderationspartner-Domäne kann nicht gleichzeitig blockiert und zugelassen werden. Lync Server 2013 verhindert, dass dies geschieht, damit Sie Ihre Listen nicht synchronisieren müssen.

        
        </div>
    
      - Wenn Sie den Zugriff auf Diese Verbunddomäne auf Benutzer eines bestimmten Servers einschränken möchten, auf dem der Access Edge-Dienst ausgeführt wird, geben Sie in **Access Edge Service (FQDN)** den FQDN des Servers der Verbunddomäne ein, auf dem der Access Edge-Dienst ausgeführt wird.
    
      - Wenn Sie zusätzliche Informationen angeben möchten, geben Sie in **Kommentar**Informationen ein, die Sie für andere Systemadministratoren über diese Konfiguration freigeben möchten.

6.  Klicken Sie auf **Commit ausführen**.

7.  Wiederholen Sie die Schritte 4 bis 6 für jede Federated-Partner-Domäne, die Sie zulassen möchten.

Zum Aktivieren des Zugriffs auf den Verbundbenutzer müssen Sie auch die Unterstützung für den Verbundbenutzer Zugriff in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Darüber hinaus müssen Sie die Richtlinie für Benutzer konfigurieren und anwenden, die in der Lage sein sollen, mit Verbundbenutzern zusammenzuarbeiten. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

