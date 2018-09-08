---
title: Verwalten von Speicherorten für SIP-Trunk-Dienstanbieter in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Entscheidungen zur Planung einer der Standortdatenbank Informationen oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mit Anbietern von SIP-Trunking in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 5920abd848645354b95c4b9ba2dc9b8a27410ef6
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887054"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Verwalten von Speicherorten für SIP-Trunk-Dienstanbieter in Skype für Business Server

Entscheidungen zur Planung einer der Standortdatenbank Informationen oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mit Anbietern von SIP-Trunking in Skype für Business Server Enterprise-VoIP.

Zum Konfigurieren von Skype für Business Server, Clients in einem Netzwerk automatisch gesucht werden soll, müssen Sie entweder die Standortinformationen Dienstdatenbank mithilfe einer netzwerkwiremap Auffüllen und veröffentlichen Sie die Standorte oder link zu einer externen Datenbank, die bereits enthält die richtigen Zuordnungen. Im Rahmen dieses Vorgangs müssen Sie die Adressen der Standorte mit Ihrem E9-1-1-Dienstanbieter abgleichen. Weitere Informationen hierzu finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

Die Datenbank des Standortinformationsdiensts füllen Sie mit einem Emergency Response Location (ERL) auf, der aus der allgemeinen Adresse und der spezifischen Adresse innerhalb eines Gebäudes besteht. Standortinformationen Service Felds **Standort** , der die Position in einem Gebäude ist, hat die maximal 20 Zeichen (einschließlich Leerzeichen). In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

- Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und die dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

- Ein Location-Bezeichner, der Benutzer auf einfache Weise angezeigt, die ihre Skype für Business Client den richtigen Speicherort aufgenommene helfen. Die Skype für Business-Client automatisch verkettet und die erkannten **Speicherort** und den **Ort** Felder in der Kopfzeile angezeigt. Eine gute Vorgehensweise ist die Straße, der das Erstellen von jedem Standort-ID hinzufügen (z. B. "1. Floor <street number>"). Ohne die Straße konnte Gebäuden in der Stadt ein Speicherortbezeichner generischen wie "1. Floor" zuweisen.

- Wenn die ungefähre erfolgt, da es von einem drahtlosen Zugriffspunkt bestimmt wird, können Sie das Wort **[in Ihrer Nähe]** (beispielsweise "in der Nähe 1. Floor 1234") hinzufügen.

> [!NOTE]
> Speicherorte der zentralen Datenbank hinzugefügt sind nicht an den Client verfügbar, bis sie über einen Skype für Business Server Management Shell-Befehl veröffentlicht und in den Pool Geschäften repliziert werden werden. Weitere Informationen hierzu finden Sie unter [Veröffentlichung der Standortdatenbank](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in der Bereitstellungsdokumentation.

In den folgenden Abschnitten erfahren Sie, was Sie beim Auffüllen und Verwalten der Standortdatenbank bedenken müssen.

## <a name="populating-the-location-database"></a>Auffüllen der Standortdatenbank

Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.

 **Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**

Wo befinden sich die Daten und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei als Batch hinzugefügt?

 **Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**

Sie können mithilfe der sekundären Standortinformationen Service-Option zum Herstellen einer Drittanbieter-Datenbank gruppieren und Verwalten von Speicherorten mithilfe einer offline-Plattform. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Dies bedeutet, dass der Dienst Standortinformationen mehrere Adressen, den sekundären standortinformationsdienst stammt, um einen Skype für Business Client zurückgegeben werden kann. Der Benutzer kann dann den am besten geeigneten Standort wählen.

Um mit dem Dienst Standortinformationen zu integrieren, muss die Drittanbieter-Datenbank führen Sie die Lync Server Speicherort Anforderung und Antwort-Schema. Weitere Informationen hierzu finden Sie unter ["[MS-E911WS]: Webdienst für E911 Unterstützung Protokollspezifikation"](https://go.microsoft.com/fwlink/p/?linkid=213819). Weitere Informationen zur Bereitstellung einer sekundären standortinformationsdienst finden Sie unter [Konfigurieren einer sekundären standortinformationsdienst in Skype für Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

## <a name="maintaining-the-location-database"></a>Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

 **Wie aktualisieren Sie die Standortdatenbank?**

Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort, oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte per Massenvorgang durch?

 **Verwenden Sie eine SNMP-Anwendung zum Abgleich von Lync-Client-MAC-Adressen mit den Port- und Switchbezeichnern?**

Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung einen Chassis-IP-Adresse oder Port-ID, die nicht in der Datenbank enthalten ist zurückgibt, werden der standortinformationsdienst nicht können einen Speicherort, an den Client zurückgegeben.


