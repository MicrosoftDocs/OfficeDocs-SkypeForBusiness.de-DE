---
title: 'Lync Server 2013: Definieren von optionalen Director-Topologien in einer Topologie'
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
ms.openlocfilehash: 86f3c78730e8c866e3838f22a1267a57bb3d237b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Definieren von optionalen Director-Topologien in einer Topologie für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Die lync Server 2013-Directors können Single-Instance-Server sein oder als Lastenausgleichspool mehrerer Directors installiert werden, um höhere Verfügbarkeit und Kapazität zu erreichen. Sowohl der Hardwarelastenausgleich als auch der DNS-Lastenausgleich (Domain Name System) werden unterstützt. In diesem Thema wird erläutert, wie Sie den DNS-Lastenausgleich für Director-Pools konfigurieren.

Um eine Topologie erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, wenn Sie eine Serverrolle hinzufügen oder entfernen, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen **RTCUniversalServerAdmins** und **Domänenadministratoren** ist. Sie können auch die richtigen Administratorrechte und-Berechtigungen für das Hinzufügen von Serverrollen delegieren. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Dokumentation zur Standard Edition-Server-oder Enterprise Edition-Server Bereitstellung. Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der **RTCUniversalServerAdmins** -Gruppe erforderlich.

In diesem Thema werden die Schritte zum Definieren und Veröffentlichen der Topologie für die beiden Director-Topologien beschrieben:

  - So definieren Sie den Director (einzelne Instanz)

  - So definieren Sie den Director (mehrere Director-Pools)

<div>

## <a name="to-define-the-director-single-instance"></a>So definieren Sie den Director (einzelne Instanz)

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Klicken Sie auf der Seite Willkommen auf **Topologie aus vorhandener Bereitstellung herunterladen**.

3.  Geben Sie im Dialogfeld **Topologie speichern** unter den Namen und den Speicherort der lokalen Kopie der vorhandenen Topologie ein, und klicken Sie auf **Speichern**.

4.  Erweitern Sie die Website, auf der Sie den Director hinzufügen möchten, klicken Sie mit der rechten Maustaste auf **Director-Pools**, und klicken Sie dann auf **Neuer Director-Pool**.

5.  Gehen Sie im Dialogfeld **Director-Pool-FQDN definieren** wie folgt vor:
    
      - Geben Sie in **Pool FQDN**den FQDN für den Director-Pool ein.
    
      - Klicken Sie auf **Einzelcomputer Pool**, und klicken Sie dann auf **weiter**.

6.  Führen Sie im Dialogfeld **Dateifreigabe definieren** eine der folgenden Aktionen aus:
    
    1.  Wenn Sie eine vorhandene Dateifreigabe verwenden möchten, klicken Sie auf **zuvor definierte Dateifreigabe verwenden**, wählen Sie eine Dateifreigabe aus der Liste aus, und klicken Sie dann auf **weiter**.
    
    2.  Wenn Sie eine neue Dateifreigabe erstellen möchten, klicken Sie auf **neue Dateifreigabe definieren**, geben Sie den FQDN für den Speicherort der Dateifreigabe unter **Datei Server-FQDN**ein, geben Sie den Namen der Freigabe in **Dateifreigabe**ein, und klicken Sie dann auf **weiter**.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Dateifreigabe, die Sie in diesem Schritt angeben oder erstellen, muss vor dem Veröffentlichen der Topologie vorhanden sein oder erstellt werden.<BR>Die einem Director zugewiesene Dateifreigabe wird nicht tatsächlich verwendet, sodass Sie die Dateifreigabe eines beliebigen Pools in der Organisation zuweisen können.

    
    </div>

7.  Geben Sie im Dialogfeld **URL für Webdienste angeben** in **externe Basis-URL**den FQDN für die Directors an, und klicken Sie dann auf **Fertig stellen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Name muss von Internet-DNS-Servern aufgelöst werden und auf die öffentliche IP-Adresse des Reverse-Proxys verweisen, der auf HTTP/HTTPS-Anforderungen an diese URL wartet und diese an das virtuelle Verzeichnis externer Webdienste in diesem Director abgibt.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein. Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie beschließen, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.

    
    </div>

8.  Veröffentlichen Sie die Topologie.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>So definieren Sie den Director (mehrere Director-Pools)

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Klicken Sie auf der Seite Willkommen auf **Topologie aus vorhandener Bereitstellung herunterladen**.

3.  Geben Sie im Dialogfeld **Topologie speichern** unter den Namen und den Speicherort der lokalen Kopie der vorhandenen Topologie ein, und klicken Sie auf **Speichern**.

4.  Erweitern Sie die Website, auf der Sie den Director hinzufügen möchten, klicken Sie mit der rechten Maustaste auf **Director-Pools**, und klicken Sie dann auf **Neuer Director-Pool**.

5.  Gehen Sie im Dialogfeld **Director-Pool-FQDN definieren** wie folgt vor:
    
      - Geben Sie in **Pool FQDN**den FQDN für den Director-Pool ein.
    
      - Klicken Sie auf **Pool mit mehreren Computern**, und klicken Sie dann auf **weiter**.

6.  Gehen Sie im Dialogfeld **Computer in diesem Pool definieren** wie folgt vor:
    
      - Geben Sie den Computer-FQDN des ersten Pool Mitglieds an, und klicken Sie dann auf **Hinzufügen**.
    
      - Wiederholen Sie den vorherigen Schritt für jeden Computer, den Sie hinzufügen möchten. Wenn Sie den Vorgang beenden, klicken Sie auf **weiter**.

7.  Führen Sie im Dialogfeld **Dateifreigabe definieren** eine der folgenden Aktionen aus:
    
      - Wenn Sie eine vorhandene Dateifreigabe verwenden möchten, klicken Sie auf **zuvor definierte Dateifreigabe verwenden**, wählen Sie eine Dateifreigabe aus der Liste aus, und klicken Sie dann auf **weiter**.
    
      - Wenn Sie eine neue Dateifreigabe erstellen möchten, klicken Sie auf **neue Dateifreigabe definieren**, geben Sie den FQDN für den Speicherort der Dateifreigabe unter **Datei Server-FQDN**ein, geben Sie den Namen der Freigabe in **Dateifreigabe**ein, und klicken Sie dann auf **weiter**.
    
    <div>
    

    > [!IMPORTANT]  
    > Die Dateifreigabe, die Sie in diesem Schritt angeben oder erstellen, muss vor dem Veröffentlichen der Topologie vorhanden sein oder erstellt werden.<BR>Die einem Director zugewiesene Dateifreigabe wird nicht tatsächlich verwendet, sodass Sie die Dateifreigabe eines beliebigen Pools in der Organisation zuweisen können.

    
    </div>

8.  Geben Sie im Dialogfeld **URL für Webdienste angeben** in **externe Basis-URL**den FQDN für die Directors an, und klicken Sie dann auf **Fertig stellen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Name muss von Internet-DNS-Servern aufgelöst werden und auf die öffentliche IP-Adresse des Reverse-Proxys verweisen, der auf HTTP/HTTPS-Anforderungen wartet, die an diese URL gesendet werden, und Sie an das virtuelle Verzeichnis externer Webdienste in diesem Director-Pool weiterleiten.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein. Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie beschließen, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.

    
    </div>

9.  Veröffentlichen Sie die Topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

