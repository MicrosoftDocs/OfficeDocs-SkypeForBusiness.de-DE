---
title: 'Lync Server 2013: Bearbeiten des Netzwerk Konfigurations Diagramms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225702f30aa19bf53c8b3f65c9731ea29b16a686
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Bearbeiten des Netzwerk Konfigurations Diagramms in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Der größte Teil der Arbeit, die ein Designer im lync Server 2013 plant, besteht darin, die Einträge für die IP-Adressen und vollqualifizierten Domänennamen (FQDNs) für die Einträge im Netzplandiagramm zu definieren. Die Informationen, die auf dieser Seite eingegeben werden, werden in die Berichte und andere im Planungs Tool enthaltene Informationen überführt.

![Planungs Tool-Netzwerkdiagramm](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planungs Tool-Netzwerkdiagramm")

Das Planungs Tool erstellt ein Netzplandiagramm mit Standardtext für IP-Adressen und FQDNs.

So bearbeiten Sie das Netzwerkdiagramm und geben Werte ein

1.  Wählen Sie einen Abschnitt des Netzwerks aus, den Sie bearbeiten möchten. Doppelklicken Sie beispielsweise auf den Text **access1.contoso.com**. Geben Sie im daraufhin geöffneten Dialogfeld den tatsächlichen FQDN des Server access1.contoso.com und die tatsächliche IP-Adresse ein, und ersetzen Sie dabei die 131.107.155.3.

2.  Klicken Sie auf **OK**, um die Einträge zu speichern.

3.  Fahren Sie mit der Bearbeitung von IP-Adressen und FQDNs fort, und geben Sie virtuelle IP-Adressen für Hardwaregeräte zum Lastenausgleich oder Servereinträge für einen DNS-Lastenausgleich (Domain Name System) für Server in Pools an.

Eine nützliche Funktion des Planungstools ist die, dass ein Bereich von IP-Adressen und Serverhostnamen inkrementell zugewiesen werden kann. Auf diese Weise muss der für den Entwurf verantwortliche Benutzer die Server in einem Pool nicht einzeln bearbeiten. Beispiel:

1.  Doppelklicken Sie auf die Front-End-Server im Pool. Wählen Sie im nun geöffneten Dialogfeld die Option **Möchten Sie IP-Adressen und FQDN als Startpunkte für alle äquivalenten Server im Cluster verwenden?**.

2.  Der Startwert für den ersten Server ist beispielsweise fe0101.contoso.com und die IP-Adresse 192.168.21.122.

3.  Geben Sie **FE0.contoso.com** in **Front-End-Server FQDN**ein, geben Sie **192.168.21.131** in **Front-End-Server IP-Adresse**ein, und klicken Sie dann auf **OK**.

4.  Das Feature für automatische Inkrementierung aktualisiert alle Server im Pool mit "fe01" über "fe06" und die gesamte IP-Adresse von 192.168.21.131 zu 136.

Nachdem Sie alle Bearbeitungen abgeschlossen haben, speichern Sie die Topologie, indem Sie die folgenden Schritte ausführen:

Klicken Sie zum Speichern des Entwurfs des Planungstools auf **Datei**, und klicken Sie dann auf **Topologie speichern** oder **Topologie speichern**unter. Wenn ein Dialogfeld **Planungstool speichern unter** angezeigt wird, geben Sie in **Dateiname** einen Namen für die Datei ein, und klicken Sie dann auf **Speichern**.

<div>

## <a name="see-also"></a>Siehe auch


[Bearbeiten des Entwurfs in lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

