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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Entscheidungen, die für die Planung einer Standortinformationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mithilfe von ELIN-Gateways in Skype for Business Server Enterprise-VoIP erforderlich sind.
ms.openlocfilehash: bb0656909866a793bc8d64635b17785020dd646d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596505"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Verwalten von Standorten für ELIN-Gateways in Skype for Business Server

Entscheidungen, die für die Planung einer Standortinformationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mithilfe von ELIN-Gateways in Skype for Business Server Enterprise-VoIP erforderlich sind.

Damit Skype for Business Server automatisch Speicherorte für Clients innerhalb eines Netzwerks bereitstellen, müssen Sie die folgenden Aufgaben ausführen:

- Füllen Sie die Standortinformationsdienst-Datenbank mit einer Netzwerkkarte auf, und schließen Sie die Notrufnummern (Emergency Location Identification Numbers, ELINs) in das Feld "CompanyName" ein.

- Veröffentlichen Sie die Standorte, damit sie für Clients in Ihrem Netzwerk verfügbar sind.

- Laden Sie die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hoch.

Ausführliche Informationen zum Ausführen dieser Aufgaben finden Sie unter [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) in der Bereitstellungsdokumentation.

> [!NOTE]
> Speicherorte, die der zentralen Standortdatenbank hinzugefügt wurden, stehen dem Client erst zur Verfügung, nachdem sie mithilfe eines befehls Skype for Business Server Verwaltungsshell veröffentlicht und in die lokalen Speicher des Pools repliziert wurden. Ausführliche Informationen finden Sie unter [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) in der Bereitstellungsdokumentation.

In diesem Abschnitt wird beschrieben, was Sie beim Planen der Aktualisierung und Verwaltung der Standortdatenbank berücksichtigen sollten.

## <a name="planning-emergency-locations"></a>Planen der Notfallstandorte

Wenn Sie ELIN-Gateways verwenden, füllen Sie die Standortinformationsdienstdatenbank mit der Adresse des Standorts, einem bestimmten Standort innerhalb eines Gebäudes und mindestens einer ELIN für jeden Standort auf. In der Planungsphase sollten Sie festlegen, wie Sie die Standorte benennen und wie Sie ELINs zuweisen möchten.

### <a name="planning-location-names"></a>Planen der Standortnamen

Das **Standortfeld** des Standortinformationsdiensts, das die spezifische Position in einem Gebäude enthält, hat eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen). In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

- Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

- Ein Standortbezeichner, mit dem Benutzer leicht erkennen können, dass ihr Client den richtigen Standort ausgewählt hat. Der Skype for Business-Client verkettet automatisch und zeigt die ermittelten **Orts-** und **Ortsfelder** in der Kopfzeile an. Eine bewährte Methode besteht darin, jedem Standortbezeichner (z. B. "1. Stock") die Straßenadresse des Gebäudes <street number> hinzuzufügen. Ohne die Straßenadresse kann ein generischer Standortbezeichner wie "1. Stock" für jedes Gebäude in der Stadt gelten.

- Wenn der Standort ungefähr ist, da er von einem drahtlosen Zugriffspunkt bestimmt wird, können Sie das Wort **[Near]** hinzufügen (z. B. "Near 1st Floor 1234").

### <a name="planning-elins"></a>Planen der ELINs

Nachdem Sie festgelegt haben, wie der Gebäudebereich in Standorte aufgeteilt werden soll, müssen Sie bestimmen, wie viele ELINs jedem Standort zugewiesen werden sollen. Beispielsweise können in einem Gebäude mit mehreren Stockwerken oder mehreren Parteien unterschiedliche Gebäudebereiche verschiedenen Notfallzonen zugewiesen werden. In der Regel wird jedes Stockwerk in einem Gebäude als Standort ausgewiesen. Jedem Standort wird dann eine oder mehrere ELINs zugewiesen, die bei einem Notruf als wählende Nummer(n) verwendet werden. Von Ihrem PSTN-Betreiber erfahren Sie, welche Telefonnummern als ELINs verwendet werden können. Die folgende Tabelle enthält ein Beispiel für Standorte für eine bestimmte Anschrift.

**Beispielstandort und ELIN-Zuweisungen**

|**Gebäudebereich**|**Standort**|**ELIN**|
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

Mithilfe der Option "Sekundärer Standortinformationsdienst" zum Herstellen einer Verbindung mit einer Drittanbieterdatenbank können Sie Standorte mithilfe einer Offlineplattform gruppieren und verwalten. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Dies bedeutet, dass der Standortinformationsdienst mehrere Adressen, die vom sekundären Standortinformationsdienst stammen, an einen Skype for Business-Client zurückgeben kann. Der Benutzer kann dann den am besten geeigneten Standort wählen.

Zur Integration in den Standortinformationsdienst muss die Drittanbieterdatenbank dem Skype for Business Server Standortanforderungs-/Antwortschema folgen. Ausführliche Informationen finden Sie unter [Webdienst für E911-Supportprotokoll.](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd) Ausführliche Informationen zum Bereitstellen eines sekundären Standortinformationsdiensts finden Sie unter [Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) in der Bereitstellungsdokumentation.

## <a name="maintaining-the-location-database"></a>Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

 **Wie aktualisieren Sie die Standortdatenbank?**

Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort, oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte per Massenvorgang durch?

 **Verwenden Sie eine SNMP-Anwendung, um Skype for Business Client-MAC-Adressen mit Port- und Switch-IDs zuzuordnen?**

Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung eine Chassis-IP-Adresse oder Port-ID zurückgibt, die nicht in der Datenbank enthalten ist, kann der Standortinformationsdienst keinen Speicherort an den Client zurückgeben.