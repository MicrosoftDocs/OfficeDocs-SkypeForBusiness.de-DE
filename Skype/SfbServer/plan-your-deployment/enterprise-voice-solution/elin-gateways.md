---
title: Verwalten von Speicherorten für Elin-Gateways in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Entscheidungen, die für die Planung einer Standort Informationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mit Elin-Gateways in Skype for Business Server Enterprise-VoIP erforderlich sind.
ms.openlocfilehash: e1645be8ed1c6188d1976d794727d0668b79c12e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276929"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Verwalten von Speicherorten für Elin-Gateways in Skype for Business Server

Entscheidungen, die für die Planung einer Standort Informationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mit Elin-Gateways in Skype for Business Server Enterprise-VoIP erforderlich sind.

Damit Skype for Business Server automatisch Standorte für Clients in einem Netzwerk bereitstellt, müssen Sie die folgenden Aufgaben ausführen:

- Füllen Sie die Datenbank des Standort Informationsdiensts mit einem Netzwerk-Wiremap, und fügen Sie die Notfall Standort-Identifikationsnummern (Elins) in das Feld Firma ein.

- Veröffentlichen Sie die Standorte, damit sie für Clients in Ihrem Netzwerk verfügbar sind.

- Laden Sie die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hoch.

Ausführliche Informationen zum Ausführen dieser Aufgaben finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

> [!NOTE]
> Speicherorte, die der zentralen Standortdatenbank hinzugefügt wurden, stehen dem Client erst zur Verfügung, wenn Sie über einen Skype for Business Server-Verwaltungsshell-Befehl veröffentlicht wurden und in den lokalen Stores des Pools repliziert werden. Ausführliche Informationen finden Sie unter [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in der Bereitstellungsdokumentation.

In diesem Abschnitt wird beschrieben, was Sie beim Planen der Aktualisierung und Verwaltung der Standortdatenbank berücksichtigen sollten.

## <a name="planning-emergency-locations"></a>Planen der Notfallstandorte

Wenn Sie Elin-Gateways verwenden, füllen Sie die standortinformationsdienst-Datenbank mit der bürgerlichen Adresse, einer bestimmten Stelle in einem Gebäude und mindestens einem Elin für jeden Standort auf. In der Planungsphase sollten Sie festlegen, wie Sie die Standorte benennen und wie Sie ELINs zuweisen möchten.

### <a name="planning-location-names"></a>Planen der Standortnamen

Das Feld standortinformationsdienst **Standort** , in dem sich die bestimmte Position in einem Gebäude befindet, hat eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen). In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

- Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und die dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

- Eine Standort-ID, die Benutzern hilft, einfach zu erkennen, dass Ihr Client den richtigen Standort übernommen hat. Der Skype for Business-Client verkettet und zeigt die Felder " **Ort** " **** und "Ort" in der Kopfzeile automatisch an. Es empfiehlt sich, jeder Standortkennung die Straßenadresse des Gebäudes hinzuzufügen (beispielsweise "1st Floor <street number>"). Ohne die Straßenadresse kann eine generische Standortkennung wie "1. Etage" für alle Gebäude in der Stadt gelten.

- Wenn der Standort Näherungswert ist, da er von einem Drahtloszugriffspunkt bestimmt wird, möchten Sie möglicherweise das Wort **[Near]** hinzufügen (beispielsweise "in der Nähe der ersten Etage 1234").

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

Mithilfe der Option sekundärer standortinformationsdienst zum Herstellen einer Verbindung mit einer Drittanbieter-Datenbank können Sie Speicherorte mithilfe einer Offline Plattform gruppieren und verwalten. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Das bedeutet, dass der standortinformationsdienst mehrere Adressen, die vom sekundären standortinformationsdienst stammen, an einen Skype for Business-Client zurückgeben kann. Der Benutzer kann dann den am besten geeigneten Standort wählen.

Zur Integration in den standortinformationsdienst muss die Drittanbieterdatenbank dem Standort Anforderungs-/Antwortschema von Skype for Business Server entsprechen. Ausführliche Informationen finden Sie unter [Support Protokoll für Web Service für E911](https://go.microsoft.com/fwlink/p/?linkid=213819). Details zum Bereitstellen eines sekundären Standort Informationsdiensts finden Sie unter [Konfigurieren eines sekundären Standort Informationsdiensts in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

## <a name="maintaining-the-location-database"></a>Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

 **Wie aktualisieren Sie die Standortdatenbank?**

Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte als Batch durch?

 **Verwenden Sie eine SNMP-Anwendung, um Skype for Business-Client-Mac-Adressen an Port-und Switch-IDs anzupassen?**

Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung eine Chassis-IP-Adresse oder Port-ID zurückgibt, die nicht in der Datenbank enthalten ist, kann der standortinformationsdienst keinen Standort an den Client zurückgeben.


