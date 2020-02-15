---
title: 'Lync Server 2013: Verwalten von Speicherorten für SIP-Trunk Dienstanbieter'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2ffa9b16a2c582af2de990eab52b55c175121bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Verwalten von Speicherorten für SIP-Trunk Dienstanbieter in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Um lync Server so zu konfigurieren, dass Clients in einem Netzwerk automatisch gefunden werden, müssen Sie entweder die Standortinformationsdienst Datenbank mit einem Netzwerk Wiremap auffüllen und die Speicherorte veröffentlichen oder eine Verbindung mit einer externen Datenbank herstellen, die bereits die richtige enthält. Zuordnungen. Im Rahmen dieses Vorgangs müssen Sie die Adressen der Standorte mit Ihrem E9-1-1-Dienstanbieter abgleichen. Ausführliche Informationen finden Sie unter [Konfigurieren der Standortdatenbank in lync Server 2013](lync-server-2013-configure-the-location-database.md) in der Bereitstellungsdokumentation.

Die Datenbank des Standortinformationsdiensts füllen Sie mit einem Emergency Response Location (ERL) auf, der aus der allgemeinen Adresse und der spezifischen Adresse innerhalb eines Gebäudes besteht. Das Feld Standortinformationsdienst **Speicherort** , bei dem es sich um eine bestimmte Position innerhalb eines Gebäudes handelt, weist eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen) auf. In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

  - Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

  - Eine Standort-ID, mit der Benutzer leicht erkennen können, dass Ihr lync-Client den richtigen Speicherort ausgewählt hat. Der lync-Client verkettet automatisch die Felder ermittelter **Speicherort** und **Ort** in der Kopfzeile und zeigt diese an. Es empfiehlt sich, die Straßenadresse des Gebäudes zu jeder Standort-ID hinzuzufügen (beispielsweise "Straßennummer \<\>1. Etage"). Ohne die Straßenadresse kann ein allgemeiner Standort Bezeichner wie "1. OG" auf alle Gebäude in der Stadt angewendet werden.

  - Wenn es sich um eine ungefähre Standortangabe handelt, da der Standort von einem Funkzugriffspunkt ermittelt wird, können Sie das Wort Near (Ca.) hinzufügen (z. B. "Ca. 1. Stock 1234").

<div>


> [!NOTE]  
> Speicherorte, die der zentralen Standortdatenbank hinzugefügt wurden, stehen dem Client erst zur Verfügung, wenn Sie mithilfe eines lync Server-Verwaltungsshell-Befehls veröffentlicht werden und in die lokalen Speicher des Pools repliziert werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-the-location-database.md">Veröffentlichen der Standortdatenbank aus lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

In den folgenden Abschnitten erfahren Sie, was Sie beim Auffüllen und Verwalten der Standortdatenbank bedenken müssen.

<div>

## <a name="populating-the-location-database"></a>Auffüllen der Standortdatenbank

Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.

  - **Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**  
    Wo befinden sich die Daten, und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei per Massenvorgang hinzugefügt?

<!-- end list -->

  - **Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**  
    Mithilfe der sekundären Standortinformationsdienst-Option von lync Server zum Herstellen einer Verbindung mit einer Drittanbieterdatenbank können Sie Standorte mithilfe einer Offline Plattform gruppieren und verwalten. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Dies bedeutet, dass der Standortinformationsdienst mehrere Adressen zurückgeben kann, die aus dem sekundären Standortinformationsdienst stammen, an einen lync Server-Client. Der Benutzer kann dann den am besten geeigneten Standort wählen.
    
    Für die Integration in die Standortinformationsdienst muss die Drittanbieterdatenbank dem lync Server standortanforderung/Antwortschema entsprechen. Ausführliche Informationen finden Sie unter\["MS-\]E911WS: Webdienst für E911-Support Protokoll Spezifikation" <http://go.microsoft.com/fwlink/p/?linkid=213819>unter. Ausführliche Informationen zum Bereitstelleneiner sekundären Standortinformationsdienst finden Sie unter [Configure a Secondary Standortinformationsdienst in lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [configure the Location Database in lync Server 2013](lync-server-2013-configure-the-location-database.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

  - **Wie aktualisieren Sie die Standortdatenbank?**  
    Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort, oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte per Massenvorgang durch?

<!-- end list -->

  - **Verwenden Sie eine SNMP-Anwendung zum Abgleich von Lync-Client-MAC-Adressen mit den Port- und Switchbezeichnern?**  
    Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung eine Gehäuse-IP-Adresse oder Port-ID zurückgibt, die nicht in der Datenbank enthalten ist, kann der Standortinformationsdienst keinen Standort an den Client zurückgeben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

