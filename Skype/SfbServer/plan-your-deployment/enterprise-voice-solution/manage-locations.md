---
title: Verwalten von Speicherorten für SIP Trunk-Dienstanbieter in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Entscheidungen, die für die Planung einer Standort Informationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mit SIP-Trunking-Anbietern in Skype for Business Server Enterprise-VoIP erforderlich sind.
ms.openlocfilehash: 81ec257b30d2916bb4df2a4590b9abfc1b270375
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802725"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Verwalten von Speicherorten für SIP Trunk-Dienstanbieter in Skype for Business Server

Entscheidungen, die für die Planung einer Standort Informationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mit SIP-Trunking-Anbietern in Skype for Business Server Enterprise-VoIP erforderlich sind.

Um Skype for Business Server so zu konfigurieren, dass Clients in einem Netzwerk automatisch gefunden werden, müssen Sie entweder die Datenbank für den standortinformationsdienst mit einem Netzwerk-Wiremap auffüllen und die Speicherorte veröffentlichen oder eine Verknüpfung mit einer externen Datenbank erstellen, die bereits vorhanden ist. die richtigen Zuordnungen. Im Rahmen dieses Vorgangs müssen Sie die Adressen der Standorte mit Ihrem E9-1-1-Dienstanbieter abgleichen. Ausführliche Informationen finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

Die Datenbank des Standortinformationsdiensts füllen Sie mit einem Emergency Response Location (ERL) auf, der aus der allgemeinen Adresse und der spezifischen Adresse innerhalb eines Gebäudes besteht. Das Feld standortinformationsdienst **Standort** , das die spezifische Position in einem Gebäude ist, hat eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen). In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

- Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und die dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

- Eine Standortkennung, die Benutzern hilft, einfach zu erkennen, dass Ihr Skype for Business-Client den richtigen Standort übernommen hat. Der Skype for Business-Client verkettet und zeigt die Felder " **Ort** " und **"Ort"** in der Kopfzeile automatisch an. Es empfiehlt sich, jeder Standortkennung die Straßenadresse des Gebäudes hinzuzufügen (beispielsweise "1st Floor <street number>"). Ohne die Straßenadresse kann eine generische Standortkennung wie "1. Etage" für alle Gebäude in der Stadt gelten.

- Wenn der Standort Näherungswert ist, da er von einem Drahtloszugriffspunkt bestimmt wird, können Sie das Wort **[Near]** hinzufügen (beispielsweise "Near First Floor 1234").

> [!NOTE]
> Speicherorte, die der zentralen Standortdatenbank hinzugefügt wurden, stehen dem Client erst zur Verfügung, wenn Sie über einen Skype for Business Server-Verwaltungsshell-Befehl veröffentlicht werden und in den lokalen Stores des Pools repliziert werden. Ausführliche Informationen finden Sie unter [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in der Bereitstellungsdokumentation.

In den folgenden Abschnitten erfahren Sie, was Sie beim Auffüllen und Verwalten der Standortdatenbank bedenken müssen.

## <a name="populating-the-location-database"></a>Auffüllen der Standortdatenbank

Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.

 **Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**

Wo befinden sich die Daten und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei als Batch hinzugefügt?

 **Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**

Mithilfe der Option sekundärer standortinformationsdienst zum Herstellen einer Verbindung mit einer Drittanbieter-Datenbank können Sie Speicherorte mithilfe einer Offline Plattform gruppieren und verwalten. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Das bedeutet, dass der standortinformationsdienst mehrere Adressen, die vom sekundären standortinformationsdienst stammen, an einen Skype for Business-Client zurückgeben kann. Der Benutzer kann dann den am besten geeigneten Standort wählen.

Zur Integration in den standortinformationsdienst muss die Drittanbieterdatenbank dem Anforderungs-/Antwortschema des lync Server-Standorts folgen. Ausführliche Informationen finden Sie unter ["[MS-E911WS]: Webdienst für E911-Support Protokoll Spezifikation"](https://go.microsoft.com/fwlink/p/?linkid=213819). Details zum Bereitstellen eines sekundären Standort Informationsdiensts finden Sie unter [Konfigurieren eines sekundären Standort Informationsdiensts in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in der Bereitstellungsdokumentation.

## <a name="maintaining-the-location-database"></a>Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

 **Wie aktualisieren Sie die Standortdatenbank?**

Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort, oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte per Massenvorgang durch?

 **Verwenden Sie eine SNMP-Anwendung zum Abgleich von Lync-Client-MAC-Adressen mit den Port- und Switchbezeichnern?**

Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung eine Chassis-IP-Adresse oder Port-ID zurückgibt, die nicht in der Datenbank enthalten ist, kann der standortinformationsdienst keinen Standort an den Client zurückgeben.


