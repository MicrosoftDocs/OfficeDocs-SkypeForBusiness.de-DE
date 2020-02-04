---
title: 'Lync Server 2013: Verwalten von Speicherorten für Elin-Gateways'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>Verwalten von Speicherorten für Elin-Gateways in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Damit lync Server automatisch Speicherorte für Clients in einem Netzwerk bereitstellt, müssen Sie die folgenden Aufgaben ausführen:

  - Füllen Sie die Datenbank des Standort Informationsdiensts mit einem Netzwerk-Wiremap, und fügen Sie die Notfall Standort-Identifikationsnummern (Elins) in das Feld Firma ein.

  - Veröffentlichen Sie die Standorte, damit sie für Clients in Ihrem Netzwerk verfügbar sind.

  - Laden Sie die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hoch.

Details zum Ausführen dieser Aufgaben finden Sie unter [Konfigurieren der Standortdatenbank in lync Server 2013](lync-server-2013-configure-the-location-database.md) in der Bereitstellungsdokumentation.

<div>


> [!NOTE]  
> Speicherorte, die der zentralen Standortdatenbank hinzugefügt wurden, stehen dem Client erst zur Verfügung, nachdem Sie mithilfe eines lync Server-Verwaltungsshell-Befehls veröffentlicht und in den lokalen Speicher des Pools repliziert wurden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-the-location-database.md">Veröffentlichen der Standortdatenbank aus lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

In diesem Abschnitt wird beschrieben, was Sie beim Planen der Aktualisierung und Verwaltung der Standortdatenbank berücksichtigen sollten.

<div>

## <a name="planning-emergency-locations"></a>Planen der Notfallstandorte

Wenn Sie Elin-Gateways verwenden, füllen Sie die standortinformationsdienst-Datenbank mit der bürgerlichen Adresse, einer bestimmten Stelle in einem Gebäude und mindestens einem Elin für jeden Standort auf. In der Planungsphase sollten Sie festlegen, wie Sie die Standorte benennen und wie Sie ELINs zuweisen möchten.

<div>

## <a name="planning-location-names"></a>Planen der Standortnamen

Das Feld standortinformationsdienst **Standort** , in dem sich die bestimmte Position in einem Gebäude befindet, hat eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen). In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

  - Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und die dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

  - Eine Standort-ID, die Benutzern hilft, einfach zu erkennen, dass Ihr lync-Client den richtigen Speicherort übernommen hat. Der lync-Client verkettet und zeigt die Felder "gefundener **Ort** " und **"Ort"** in der Kopfzeile automatisch an. Eine gute Vorgehensweise besteht darin, jeder Standortkennung die Straßenadresse des Gebäudes hinzuzufügen (zum Beispiel " \<Straßennummer\>1. Etage"). Ohne die Straßenadresse kann eine generische Standortkennung wie "1. Etage" für alle Gebäude in der Stadt gelten.

  - Wenn es sich um eine ungefähre Standortangabe handelt, da der Standort von einem Funkzugriffspunkt ermittelt wird, sollten Sie das Wort Near (Ca.) hinzufügen (z. B. „Ca. 1. Stock 1234“).

</div>

<div>

## <a name="planning-elins"></a>Planen der ELINs

Nachdem Sie festgelegt haben, wie der Gebäudebereich in Standorte aufgeteilt werden soll, müssen Sie bestimmen, wie viele ELINs jedem Standort zugewiesen werden sollen. Beispielsweise können in einem Gebäude mit mehreren Stockwerken oder mehreren Parteien unterschiedliche Gebäudebereiche verschiedenen Notfallzonen zugewiesen werden. In der Regel wird jedes Stockwerk in einem Gebäude als Standort ausgewiesen. Jedem Standort werden dann ELINs zugewiesen, die bei einem Notruf als wählende Nummern verwendet werden. Von Ihrem PSTN-Betreiber erfahren Sie, welche Telefonnummern als ELINs verwendet werden können. Die folgende Tabelle enthält ein Beispiel für Standorte für eine bestimmte Anschrift.

### <a name="sample-location-and-elin-assignments"></a>Beispielstandort und ELIN-Zuweisungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gebäudebereich</th>
<th>Ort</th>
<th>ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Erster Stock</p></td>
<td><p>1</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>Zweiter Stock</p></td>
<td><p>2</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>Dritter Stock</p></td>
<td><p>3</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


Die von Ihnen definierten Standorte sollten die folgenden Anforderungen erfüllen:

  - Lokale und nationale/regionale Bestimmungen im Hinblick auf den maximalen Bereich pro Standort und die Anzahl von Standorten pro Anschrift werden eingehalten.

  - Sie sind aussagekräftig genug, damit die Person, die den Notruf getätigt hat, problemlos auffindbar ist.

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>Auffüllen der Standortdatenbank

Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.

  - **Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**  
    Wo befinden sich die Daten und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei als Batch hinzugefügt?

<!-- end list -->

  - **Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**  
    Wenn Sie die Option sekundärer standortinformationsdienst von lync Server zum Herstellen einer Verbindung mit einer Drittanbieter-Datenbank verwenden, können Sie Speicherorte mithilfe einer Offline Plattform gruppieren und verwalten. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Dies bedeutet, dass der standortinformationsdienst mehrere Adressen, die vom sekundären standortinformationsdienst stammen, an einen lync Server-Client zurückgeben kann. Der Benutzer kann dann den am besten geeigneten Standort wählen.
    
    Zur Integration in den standortinformationsdienst muss die Drittanbieterdatenbank dem Anforderungs-/Antwortschema des lync Server-Standorts folgen. Ausführliche Informationen finden Sie <http://go.microsoft.com/fwlink/p/?linkid=213819>unter. Details zum Bereitstellen eines sekundären Standort Informationsdiensts finden Sie unter [Konfigurieren eines sekundären Standort Informationsdiensts in lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in der Bereitstellungsdokumentation.

Details zum Auffüllen der Standortdatenbank finden Sie unter [Konfigurieren der Standortdatenbank in lync Server 2013](lync-server-2013-configure-the-location-database.md) in der Bereitstellungsdokumentation.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

  - **Wie aktualisieren Sie die Standortdatenbank?**  
    Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte als Batch durch?

<!-- end list -->

  - **Verwenden Sie eine SNMP-Anwendung zum Abgleich von Lync-Client-MAC-Adressen mit den Port- und Switchbezeichnern?**  
    Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung eine Chassis-IP-Adresse oder Port-ID zurückgibt, die nicht in der Datenbank enthalten ist, kann der standortinformationsdienst keinen Standort an den Client zurückgeben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

