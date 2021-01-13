---
title: Verwalten von Standorten für ELIN-Gateways in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Entscheidungen, die für die Planung einer Standortinformationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mit ELIN-Gateways in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 387b94ca59ef7750a80d06c88b371a0afef9313d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834395"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Verwalten von Standorten für ELIN-Gateways in Skype for Business Server

Entscheidungen, die für die Planung einer Standortinformationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mit ELIN-Gateways in Skype for Business Server Enterprise-VoIP.

Damit Skype for Business Server automatisch Standorte für Clients innerhalb eines Netzwerks bereitstellen kann, müssen Sie die folgenden Aufgaben ausführen:

- Füllen Sie die Standortinformationsdienstdatenbank mit einer Netzwerkverbindungskarte auf, und schließen Sie die ELINs (Emergency Location Identification Numbers) in das Feld "CompanyName" ein.

- Veröffentlichen Sie die Standorte, damit sie für Clients in Ihrem Netzwerk verfügbar sind.

- Laden Sie die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hoch.

Ausführliche Informationen zum Ausführen dieser Aufgaben finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

> [!NOTE]
> Standorte, die der zentralen Standortdatenbank hinzugefügt wurden, stehen dem Client erst zur Verfügung, wenn sie mithilfe eines Skype for Business Server-Verwaltungsshell-Befehls veröffentlicht und in die lokalen Speicher des Pools repliziert wurden. Ausführliche Informationen finden Sie unter [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in der Bereitstellungsdokumentation.

In diesem Abschnitt wird beschrieben, was Sie beim Planen der Aktualisierung und Verwaltung der Standortdatenbank berücksichtigen sollten.

## <a name="planning-emergency-locations"></a>Planen der Notfallstandorte

Bei Verwendung von ELIN-Gateways füllen Sie die Standortinformationsdienstdatenbank mit der adresse, einem bestimmten Standort innerhalb eines Gebäudes und mindestens einer ELIN für jeden Standort auf. In der Planungsphase sollten Sie festlegen, wie Sie die Standorte benennen und wie Sie ELINs zuweisen möchten.

### <a name="planning-location-names"></a>Planen der Standortnamen

Das Feld "Standort" **des** Standortinformationsdiensts, das den bestimmten Standort in einem Gebäude enthält, hat eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen). In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

- Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

- Eine Standort-ID, mit der Benutzer leicht erkennen können, dass ihr Client den richtigen Standort ausgewählt hat. Der Skype for Business-Client verkn nen die ermittelten Felder **"Standort"** und "Ort" automatisch verkn nen und in der Kopfzeile anzeigen.  Eine bewährte Methode besteht im Hinzufügen der Straße des Gebäudes zu jedem Standortbezeichner (z. B. "1. <street number> Stock"). Ohne die Anschrift könnte ein generischer Standortbezeichner wie "1. Stock" für jedes Gebäude in der Stadt gelten.

- Wenn der Standort ungefähr ist, da er von einem Funkzugriffspunkt bestimmt wird, können Sie das Wort **[Near]** hinzufügen (z. B. "Near 1st Floor 1234").

### <a name="planning-elins"></a>Planen der ELINs

Nachdem Sie festgelegt haben, wie der Gebäudebereich in Standorte aufgeteilt werden soll, müssen Sie bestimmen, wie viele ELINs jedem Standort zugewiesen werden sollen. Beispielsweise können in einem Gebäude mit mehreren Stockwerken oder mehreren Parteien unterschiedliche Gebäudebereiche verschiedenen Notfallzonen zugewiesen werden. In der Regel wird jedes Stockwerk in einem Gebäude als Standort ausgewiesen. Jedem Standort wird dann eine oder mehrere ELINs zugewiesen, die bei einem Notruf als wählende Nummer(n) verwendet werden. Von Ihrem PSTN-Betreiber erfahren Sie, welche Telefonnummern als ELINs verwendet werden können. Die folgende Tabelle enthält ein Beispiel für Standorte für eine bestimmte Anschrift.

**Beispielstandort und ELIN-Zuweisungen**

|**Gebäudebereich**|**Ort**|**ELIN**|
|:-----|:-----|:-----|
|Erster Stock  <br/> |1   <br/> |425-555-0100  <br/> |
|Zweiter Stock  <br/> |2   <br/> |425-555-0111  <br/> |
|Dritter Stock  <br/> |3   <br/> |425-555-0123  <br/> |

Die von Ihnen definierten Standorte sollten die folgenden Anforderungen erfüllen:

- Lokale und nationale/regionale Bestimmungen werden im Hinblick auf den maximalen Bereich pro Standort und die Anzahl von Standorten pro Anschrift eingehalten.

- Sie sind aussagekräftig genug, damit die Person, die den Notruf getätigt hat, problemlos auffindbar ist.

## <a name="populating-the-location-database"></a>Auffüllen der Standortdatenbank

Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.

 **Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**

Wo befinden sich die Daten, und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei per Massenvorgang hinzugefügt?

 **Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**

Mithilfe der Option "Sekundärer Standortinformationsdienst" zum Herstellen einer Verbindung mit einer Drittanbieterdatenbank können Sie Standorte mithilfe einer Offlineplattform gruppieren und verwalten. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Dies bedeutet, dass der Standortinformationsdienst mehrere Adressen aus dem sekundären Standortinformationsdienst an einen Skype for Business-Client zurückgeben kann. Der Benutzer kann dann den am besten geeigneten Standort wählen.

Für die Integration in den Standortinformationsdienst muss die Drittanbieterdatenbank dem Skype for Business Server Location Request/Response-Schema folgen. Weitere Informationen finden Sie [unter Web Service for E911 Support Protocol](https://go.microsoft.com/fwlink/p/?linkid=213819). Ausführliche Informationen zum Bereitstellen eines sekundären Standortinformationsdiensts finden Sie unter "Konfigurieren eines sekundären Standortinformationsdiensts [in Skype for Business Server" in](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) der Bereitstellungsdokumentation.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

## <a name="maintaining-the-location-database"></a>Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

 **Wie aktualisieren Sie die Standortdatenbank?**

Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort, oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte per Massenvorgang durch?

 **Verwenden Sie eine SNMP-Anwendung, um Skype for Business-Client-MAC-Adressen mit Port- und Switchbezeichnern zu übereinstimmen?**

Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung eine Chassis-IP-Adresse oder Port-ID zurückgibt, die nicht in der Datenbank enthalten ist, kann der Standortinformationsdienst keinen Standort an den Client zurückgeben.


