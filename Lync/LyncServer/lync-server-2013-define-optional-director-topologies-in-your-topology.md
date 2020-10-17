---
title: 'Lync Server 2013: Definieren von optionalen Director-Topologien in Ihrer Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e53512d2d3c0bd99c4d5b23d20f21859ec974415
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504572"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Definieren von optionalen Director-Topologien in Ihrer Topologie für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Lync Server 2013 Directors können Einzelinstanzen Server sein oder als Pool mit Lastenausgleich von mehreren Directors installiert werden, um höhere Verfügbarkeit und Kapazität zu erreichen. Sowohl Hardwarelastenausgleich als auch Domain Name System (DNS) Lastenausgleich werden unterstützt. In diesem Thema wird erläutert, wie Sie den DNS-Lastenausgleich für Director-Pools konfigurieren.

Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen **RTCUniversalServerAdmins** und **Domänen-Admins** angemeldet sein. Außerdem können Sie die erforderlichen Berechtigungen für das Hinzufügen von Serverrollen delegieren. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Standard Edition-Server-oder Enterprise Edition-Server-Bereitstellungsdokumentation. Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe **RTCUniversalServerAdmins** sein.

In diesem Thema werden die Schritte zum Definieren und Veröffentlichen der Topologie für die beiden Director-Topologien beschrieben:

  - So definieren Sie den Director (Einzelinstanz)

  - So definieren Sie den Director (Pool mit mehreren Directors)

<div>

## <a name="to-define-the-director-single-instance"></a>So definieren Sie den Director (Einzelinstanz)

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Klicken Sie auf der Willkommenseite auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**.

3.  Geben Sie im Dialogfeld **Topologie speichern unter** den Namen und den Speicherort für die lokale Kopie der vorhandenen Topologie ein, und klicken Sie auf **Speichern**.

4.  Erweitern Sie den Standort, an dem der Director hinzugefügt werden soll, klicken Sie mit der rechten Maustaste auf **Director-Pools** und anschließend auf **Neuer Director-Pool**.

5.  Führen Sie im Dialogfeld **FQDN für Director-Pool definieren** die folgenden Schritte aus:
    
      - Geben Sie in **Pool-FQDN** den FQDN für den Director-Pool ein.
    
      - Klicken Sie auf **Pool mit einem Computer** und dann auf **Weiter**.

6.  Führen Sie im Dialogfeld **Dateifreigabe definieren** einen der folgenden Schritte aus:
    
    1.  Zum Verwenden einer vorhandenen Dateifreigabe klicken Sie auf **Zuvor definierte Dateifreigabe verwenden**, wählen Sie eine Dateifreigabe aus der Liste aus, und klicken Sie auf **Weiter**.
    
    2.  Zum Erstellen einer neuen Dateifreigabe klicken Sie auf **Neue Dateifreigabe definieren**, geben Sie in **Dateiserver-FQDN** den FQDN für das Verzeichnis der Dateifreigabe ein, geben Sie in **Dateifreigabe** den Namen der Freigabe ein, und klicken Sie anschließend auf **Weiter**.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Dateifreigabe, die Sie in diesem Schritt angeben oder erstellen, muss vor der Veröffentlichung der Topologie vorhanden sein oder erstellt werden.<BR>Die einem Director zugewiesene Dateifreigabe wird nicht tatsächlich verwendet, Sie können dem Director also die Dateifreigabe jedes Pools in der Organisation zuweisen.

    
    </div>

7.  Geben Sie im Dialogfeld **Webdienste-URL angeben** in **Externe Basis-URL** den FQDN für die Directors an, und klicken Sie anschließend auf **Fertig stellen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Name muss von Internet-DNS-Servern aufgelöst werden können und auf die öffentliche IP-Adresse des Reverseproxys verweisen, der an diese URL gesendete HTTP/HTTPS-Anforderungen überwacht und diese an das virtuelle Verzeichnis der externen Webdienste auf diesem Director weiterleitet.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server der FQDN der externen Webdienste eindeutig sein muss. Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für eine andere Front-End-Pool oder Front-End-Server verwenden. Wenn Sie auch Directors bereitstellen, muss der FQDN für externe Webdienste, der für einen Director-oder Directorpool definiert ist, von einem anderen Director oder Directorpool sowie von Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.

    
    </div>

8.  Veröffentlichen Sie die Topologie.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>So definieren Sie den Director (Pool mit mehreren Directors)

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Klicken Sie auf der Willkommenseite auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**.

3.  Geben Sie im Dialogfeld **Topologie speichern unter** den Namen und den Speicherort für die lokale Kopie der vorhandenen Topologie ein, und klicken Sie auf **Speichern**.

4.  Erweitern Sie den Standort, an dem der Director hinzugefügt werden soll, klicken Sie mit der rechten Maustaste auf **Director-Pools** und anschließend auf **Neuer Director-Pool**.

5.  Führen Sie im Dialogfeld **FQDN für Director-Pool definieren** die folgenden Schritte aus:
    
      - Geben Sie in **Pool-FQDN** den FQDN für den Director-Pool ein.
    
      - Klicken Sie auf **Pool mit mehreren Computern** und dann auf **Weiter**.

6.  Führen Sie im Dialogfeld **Computer in diesem Pool definieren** die folgenden Schritte aus:
    
      - Geben Sie den Computer-FQDN des ersten Mitglieds im Pool an, und klicken Sie anschließend auf **Hinzufügen**.
    
      - Wiederholen Sie diesen Schritt für jeden Computer, den Sie hinzufügen möchten, und klicken Sie zum Schluss auf **Weiter**.

7.  Führen Sie im Dialogfeld **Dateifreigabe definieren** einen der folgenden Schritte aus:
    
      - Zum Verwenden einer vorhandenen Dateifreigabe klicken Sie auf **Zuvor definierte Dateifreigabe verwenden**, wählen Sie eine Dateifreigabe aus der Liste aus, und klicken Sie auf **Weiter**.
    
      - Zum Erstellen einer neuen Dateifreigabe klicken Sie auf **Neue Dateifreigabe definieren**, geben Sie in **Dateiserver-FQDN** den FQDN für das Verzeichnis der Dateifreigabe ein, geben Sie in **Dateifreigabe** den Namen der Freigabe ein, und klicken Sie anschließend auf **Weiter**.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Dateifreigabe, die Sie in diesem Schritt angeben oder erstellen, muss vor der Veröffentlichung der Topologie vorhanden sein oder erstellt werden.<BR>Die einem Director zugewiesene Dateifreigabe wird nicht tatsächlich verwendet, Sie können dem Director also die Dateifreigabe jedes Pools in der Organisation zuweisen.

    
    </div>

8.  Geben Sie im Dialogfeld **Webdienste-URL angeben** in **Externe Basis-URL** den FQDN für die Directors an, und klicken Sie anschließend auf **Fertig stellen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Name muss von Internet-DNS-Servern aufgelöst werden können und auf die öffentliche IP-Adresse des Reverseproxys verweisen, der an diese URL gesendete HTTP/HTTPS-Anforderungen überwacht und diese an das virtuelle Verzeichnis der externen Webdienste in diesem Director-Pool weiterleitet.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server der FQDN der externen Webdienste eindeutig sein muss. Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für eine andere Front-End-Pool oder Front-End-Server verwenden. Wenn Sie auch Directors bereitstellen, muss der FQDN für externe Webdienste, der für einen Director-oder Directorpool definiert ist, von einem anderen Director oder Directorpool sowie von Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.

    
    </div>

9.  Veröffentlichen Sie die Topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

