---
title: Verwalten von Speicherorten für ELIN-Gateways in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Entscheidungen zur Planung einer der Standortdatenbank Informationen oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mit ELIN-Gateways in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 09397c84e69ee9df2c40bd1783c8f57a58aa21d4
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252919"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Verwalten von Speicherorten für ELIN-Gateways in Skype für Business Server

Entscheidungen zur Planung einer der Standortdatenbank Informationen oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mit ELIN-Gateways in Skype für Business Server Enterprise-VoIP.

Damit Skype für Business Server automatisch Standorte für Clients in einem Netzwerk bereitstellt, müssen Sie die folgenden Aufgaben ausführen:

- Füllen Sie die Standortinformationen Dienstdatenbank mithilfe einer netzwerkwiremap und enthalten Sie Emergency Location Identification Numbers (ELINs) im Feld CompanyName.

- Veröffentlichen Sie die Standorte, damit sie für Clients in Ihrem Netzwerk verfügbar sind.

- Laden Sie die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hoch.

Ausführliche Informationen zum Ausführen dieser Aufgaben finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

> [!NOTE]
> Speicherorte der zentralen Datenbank hinzugefügt sind nicht an den Client verfügbar, bis sie mithilfe einer Skype für Business Server Management Shell-Befehl veröffentlicht wurden und in den Pool Geschäften repliziert werden. Weitere Informationen hierzu finden Sie unter [Veröffentlichung der Standortdatenbank](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in der Bereitstellungsdokumentation.

In diesem Abschnitt wird beschrieben, was Sie beim Planen der Aktualisierung und Verwaltung der Standortdatenbank berücksichtigen sollten.

## <a name="planning-emergency-locations"></a>Planen der Notfallstandorte

Wenn Sie ELIN-Gateways verwenden, füllen Sie die Standortinformationen Service-Datenbank mit die Anschrift, einer bestimmten Position in einem Gebäude und mindestens ein ELIN für jeden Standort. In der Planungsphase sollten Sie festlegen, wie Sie die Standorte benennen und wie Sie ELINs zuweisen möchten.

### <a name="planning-location-names"></a>Planen der Standortnamen

Die Standortinformationen Service **Speicherort** -Felds, die die Position in einem Gebäude enthält, hat die maximal 20 Zeichen (einschließlich Leerzeichen). In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

- Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und die dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

- Ein Location-Bezeichner, der Benutzer auf einfache Weise angezeigt, die ihren Client den richtigen Speicherort aufgenommene helfen. Die Skype für Business-Client automatisch verkettet und die erkannten **Speicherort** und den **Ort** Felder in der Kopfzeile angezeigt. Eine gute Vorgehensweise ist die Straße, der das Erstellen von jedem Standort-ID hinzufügen (z. B. "1. Floor <street number>"). Ohne die Straße konnte Gebäuden in der Stadt ein Speicherortbezeichner generischen wie "1. Floor" zuweisen.

- Wenn die ungefähre erfolgt, da es von einem drahtlosen Zugriffspunkt bestimmt wird, können Sie das Wort **[in Ihrer Nähe]** (beispielsweise "in der Nähe 1. Floor 1234") hinzufügen möchten.

### <a name="planning-elins"></a>Planen der ELINs

Nachdem Sie festgelegt haben, wie der Gebäudebereich in Standorte aufgeteilt werden soll, müssen Sie bestimmen, wie viele ELINs jedem Standort zugewiesen werden sollen. Beispielsweise können in einem Gebäude mit mehreren Stockwerken oder mehreren Parteien unterschiedliche Gebäudebereiche verschiedenen Notfallzonen zugewiesen werden. In der Regel wird jedes Stockwerk in einem Gebäude als Standort ausgewiesen. Jedem Standort werden dann ELINs zugewiesen, die bei einem Notruf als wählende Nummern verwendet werden. Von Ihrem PSTN-Betreiber erfahren Sie, welche Telefonnummern als ELINs verwendet werden können. Die folgende Tabelle enthält ein Beispiel für Standorte für eine bestimmte Anschrift.

**Beispielstandort und ELIN-Zuweisungen**

|**Gebäudebereich**|**Standort**|**ELIN**|
|:-----|:-----|:-----|
|Erster Stock  <br/> |1  <br/> |425-555-0100  <br/> |
|Zweiter Stock  <br/> |2  <br/> |425-555-0111  <br/> |
|Dritter Stock  <br/> |3  <br/> |425-555-0123  <br/> |

Die von Ihnen definierten Standorte sollten die folgenden Anforderungen erfüllen:

- Lokale und nationale/regionale Bestimmungen im Hinblick auf den maximalen Bereich pro Standort und die Anzahl von Standorten pro Anschrift werden eingehalten.

- Sie sind aussagekräftig genug, damit die Person, die den Notruf getätigt hat, problemlos auffindbar ist.

## <a name="populating-the-location-database"></a>Auffüllen der Standortdatenbank

Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.

 **Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**

Wo befinden sich die Daten und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei als Batch hinzugefügt?

 **Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**

Sie können mithilfe der sekundären Standortinformationen Service-Option zum Herstellen einer Drittanbieter-Datenbank gruppieren und Verwalten von Speicherorten mithilfe einer offline-Plattform. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Dies bedeutet, dass der Dienst Standortinformationen mehrere Adressen, den sekundären standortinformationsdienst stammt, um einen Skype für Business Client zurückgegeben werden kann. Der Benutzer kann dann den am besten geeigneten Standort wählen.

Um mit dem Dienst Standortinformationen zu integrieren, muss die Drittanbieter-Datenbank die Skype für Business Server Speicherort Anforderung und Antwort-Schema befolgen. Weitere Informationen hierzu finden Sie unter [Webdienst für E911 Unterstützung Protokoll](https://go.microsoft.com/fwlink/p/?linkid=213819). Weitere Informationen zur Bereitstellung einer sekundären standortinformationsdienst finden Sie unter [Konfigurieren einer sekundären standortinformationsdienst in Skype für Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

## <a name="maintaining-the-location-database"></a>Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

 **Wie aktualisieren Sie die Standortdatenbank?**

Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte als Batch durch?

 **Verwenden Sie eine SNMP-Anwendung zum Abgleich von Skype für Business-Client-MAC-Adressen mit den Port- und switchbezeichnern?**

Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung einen Chassis-IP-Adresse oder Port-ID, die nicht in der Datenbank enthalten ist zurückgibt, werden der standortinformationsdienst nicht können einen Speicherort, an den Client zurückgegeben.


