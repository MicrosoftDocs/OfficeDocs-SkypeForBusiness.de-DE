---
title: Verwalten von Standorten für SIP-Trunk-Dienstanbieter in Skype for Business Server
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Entscheidungen, die für die Planung einer Standortinformationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mithilfe von SIP-Trunking-Anbietern in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 9918fc2cb6bc9d05166d648ab3285a964d15f290
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825435"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Verwalten von Standorten für SIP-Trunk-Dienstanbieter in Skype for Business Server

Entscheidungen, die für die Planung einer Standortinformationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mithilfe von SIP-Trunking-Anbietern in Skype for Business Server Enterprise-VoIP.

Um Skype for Business Server so zu konfigurieren, dass Clients in einem Netzwerk automatisch gefunden werden, müssen Sie entweder die Standortinformationsdienstdatenbank mit einer Netzwerkverbindung füllen und die Standorte veröffentlichen oder eine Verknüpfung mit einer externen Datenbank herstellen, die bereits die richtigen Zuordnungen enthält. Im Rahmen dieses Vorgangs müssen Sie die Adressen der Standorte mit Ihrem E9-1-1-Dienstanbieter abgleichen. Ausführliche Informationen finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

Die Datenbank des Standortinformationsdiensts füllen Sie mit einem Emergency Response Location (ERL) auf, der aus der allgemeinen Adresse und der spezifischen Adresse innerhalb eines Gebäudes besteht. Das Feld **"Standort** des Standortinformationsdiensts", bei dem es sich um den spezifischen Standort innerhalb eines Gebäudes handelt, hat eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen). In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

- Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

- Eine Standort-ID, mit der Benutzer leicht erkennen können, dass ihr Skype for Business-Client den richtigen Standort ausgewählt hat. Der Skype for Business-Client verkn nen die ermittelten Felder **"Standort"** und "Ort" automatisch verkn nen und in der Kopfzeile anzeigen.  Eine bewährte Methode besteht im Hinzufügen der Straße des Gebäudes zu jedem Standortbezeichner (z. B. "1. <street number> Stock"). Ohne die Anschrift könnte ein generischer Standortbezeichner wie "1. Stock" für jedes Gebäude in der Stadt gelten.

- Wenn der Standort ungefähr ist, da er von einem Funkzugriffspunkt bestimmt wird, können Sie das Wort **[Near]** hinzufügen (z. B. "Near 1st Floor 1234").

> [!NOTE]
> Standorte, die der zentralen Standortdatenbank hinzugefügt wurden, stehen dem Client erst zur Verfügung, wenn sie mithilfe eines Skype for Business Server-Verwaltungsshell-Befehls veröffentlicht und in die lokalen Speicher des Pools repliziert werden. Ausführliche Informationen finden Sie unter [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in der Bereitstellungsdokumentation.

In den folgenden Abschnitten erfahren Sie, was Sie beim Auffüllen und Verwalten der Standortdatenbank bedenken müssen.

## <a name="populating-the-location-database"></a>Auffüllen der Standortdatenbank

Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.

 **Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**

Wo befinden sich die Daten, und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei per Massenvorgang hinzugefügt?

 **Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**

Mithilfe der Option "Sekundärer Standortinformationsdienst" zum Herstellen einer Verbindung mit einer Drittanbieterdatenbank können Sie Standorte mithilfe einer Offlineplattform gruppieren und verwalten. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Dies bedeutet, dass der Standortinformationsdienst mehrere Adressen aus dem sekundären Standortinformationsdienst an einen Skype for Business-Client zurückgeben kann. Der Benutzer kann dann den am besten geeigneten Standort wählen.

Für die Integration in den Standortinformationsdienst muss die Drittanbieterdatenbank dem Lync Server Location Request/Response-Schema folgen. Weitere Informationen finden Sie unter  ["[MS-E911WS]: Web Service for E911 Support Protocol Specification"](https://go.microsoft.com/fwlink/p/?linkid=213819). Ausführliche Informationen zum Bereitstellen eines sekundären Standortinformationsdiensts finden Sie unter "Konfigurieren eines sekundären Standortinformationsdiensts [in Skype for Business Server"](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

## <a name="maintaining-the-location-database"></a>Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

 **Wie aktualisieren Sie die Standortdatenbank?**

Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort, oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte per Massenvorgang durch?

 **Verwenden Sie eine SNMP-Anwendung zum Abgleich von Lync-Client-MAC-Adressen mit den Port- und Switchbezeichnern?**

Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung eine Chassis-IP-Adresse oder Port-ID zurückgibt, die nicht in der Datenbank enthalten ist, kann der Standortinformationsdienst keinen Standort an den Client zurückgeben.


