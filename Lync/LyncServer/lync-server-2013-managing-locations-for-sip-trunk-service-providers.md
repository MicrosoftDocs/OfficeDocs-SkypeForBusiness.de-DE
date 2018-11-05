---
title: 'Lync Server 2013: Verwalten von Standorten für SIP-Trunkdienstanbieter'
TOCTitle: Verwalten von Standorten für SIP-Trunkdienstanbieter
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398959(v=OCS.15)
ms:contentKeyID: 49295587
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Standorten für SIP-Trunkdienstanbieter in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Zum Konfigurieren von Lync Server für das automatische Suchen von Clients in einem Netzwerk müssen Sie entweder die Datenbank des Standortinformationsdiensts mit einer Netzwerkwiremap auffüllen und die Standorte veröffentlichen, oder Sie stellen eine Verknüpfung zu einer externen Datenbank her, die bereits die richtigen Zuordnungen enthält. Im Rahmen dieses Vorgangs müssen Sie die Adressen der Standorte mit Ihrem E9-1-1-Dienstanbieter abgleichen. Ausführliche Informationen finden Sie unter [Konfigurieren der Standortdatenbank in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in der Bereitstellungsdokumentation.

Die Datenbank des Standortinformationsdiensts füllen Sie mit einem Emergency Response Location (ERL) auf, der aus der allgemeinen Adresse und der spezifischen Adresse innerhalb eines Gebäudes besteht. Das Feld **Location** des Standortinformationsdiensts, in dem der Standort innerhalb eines Gebäudes gespeichert ist, hat eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen). In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

  - Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

  - Einen Standortbezeichner, mit dem Benutzer problemlos erkennen können, dass der Lync-Client den richtigen Standort ermittelt hat. Die ermittelten Felder **Location** und **City** werden vom Lync-Client automatisch verkettet und im Header angezeigt. Es empfiehlt sich, die Gebäudeanschrift jedem Standortbezeichner hinzuzufügen (z. B. "1. Stock \<Hausnummer\>"). Ohne die Anschrift könnte ein allgemeiner Standortbezeichner wie z. B. "1. Stock" auf jedes Gebäude in der Stadt zutreffen.

  - Wenn es sich um eine ungefähre Standortangabe handelt, da der Standort von einem Funkzugriffspunkt ermittelt wird, können Sie das Wort Near (Ca.) hinzufügen (z. B. "Ca. 1. Stock 1234").


> [!NOTE]
> Standorte, die der zentralen Standortdatenbank hinzugefügt wurden, stehen dem Client erst zur Verfügung, nachdem sie mit einem Lync Server-Verwaltungsshell-Befehl veröffentlicht und in die lokalen Speicher des Pools repliziert wurden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-the-location-database.md">Veröffentlichen der Standortdatenbank von Lync Server 2013</A> in der Bereitstellungsdokumentation.



In den folgenden Abschnitten erfahren Sie, was Sie beim Auffüllen und Verwalten der Standortdatenbank bedenken müssen.

## Auffüllen der Standortdatenbank

Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.

  - **Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**  
    Wo befinden sich die Daten, und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei per Massenvorgang hinzugefügt?

<!-- end list -->

  - **Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**  
    Indem Sie den sekundären Standortinformationsdienst von Lync Server für die Verbindung mit einer Drittanbieterdatenbank verwenden, können Sie Standorte mithilfe einer Offlineplattform gruppieren und verwalten. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Das bedeutet, dass der Standortinformationsdienst mehrere Adressen, die vom sekundären Standortinformationsdienst stammen, an einen Lync Server-Client übermitteln kann. Der Benutzer kann dann den am besten geeigneten Standort wählen.
    
    Zur Integration in den Standortinformationsdienst muss die Drittanbieterdatenbank das Anforderung/Antwort-Schema für Standorte von Lync Server verwenden. Ausführliche Informationen finden Sie im Thema "\[MS-E911WS\]: Webdienst für die E911-Supportprotokollspezifikation" unter <http://go.microsoft.com/fwlink/p/?linkid=213819>. Ausführliche Informationen zum Bereitstellen eines sekundären Standortinformationsdiensts finden Sie unter [Konfigurieren eines sekundären Standortinformationsdiensts in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [Konfigurieren der Standortdatenbank in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in der Bereitstellungsdokumentation.

## Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

  - **Wie aktualisieren Sie die Standortdatenbank?**  
    Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort, oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte per Massenvorgang durch?

<!-- end list -->

  - **Verwenden Sie eine SNMP-Anwendung zum Abgleich von Lync-Client-MAC-Adressen mit den Port- und Switchbezeichnern?**  
    Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung eine Switch-IP-Adresse ausgibt, die nicht in der Standortdatenbank enthalten ist, kann der Standortinformationsdienst keinen Standort an den Client zurückgeben.

