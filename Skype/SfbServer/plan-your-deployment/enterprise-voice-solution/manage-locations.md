---
title: Verwalten von Standorten für SIP-Trunkdienstanbieter in Skype for Business Server
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
description: Entscheidungen, die für die Planung einer Standortinformationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mithilfe von SIP-Trunkinganbietern erforderlich sind, in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: b175c2cc3d0ed02a124a365787c8cb5d7cd37d10
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101441"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Verwalten von Standorten für SIP-Trunkdienstanbieter in Skype for Business Server

Entscheidungen, die für die Planung einer Standortinformationsdatenbank oder einer ähnlichen externen Datenbank für eine E9-1-1-Bereitstellung mithilfe von SIP-Trunkinganbietern erforderlich sind, in Skype for Business Server Enterprise-VoIP.

Um Skype for Business Server so zu konfigurieren, dass Clients in einem Netzwerk automatisch gefunden werden, müssen Sie entweder die Standortinformationsdienstdatenbank mit einer Netzwerkverbindungskarte auffüllen und die Speicherorte veröffentlichen oder eine Verknüpfung zu einer externen Datenbank herstellen, die bereits die richtigen Zuordnungen enthält. Im Rahmen dieses Vorgangs müssen Sie die Adressen der Standorte mit Ihrem E9-1-1-Dienstanbieter abgleichen. Ausführliche Informationen finden Sie unter [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) in der Bereitstellungsdokumentation.

Die Datenbank des Standortinformationsdiensts füllen Sie mit einem Emergency Response Location (ERL) auf, der aus der allgemeinen Adresse und der spezifischen Adresse innerhalb eines Gebäudes besteht. Das Feld **Standortinformationsdienst,** bei dem es sich um den spezifischen Standort in einem Gebäude handelt, hat eine maximale Länge von 20 Zeichen (einschließlich Leerzeichen). In diesem Feld mit begrenzter Länge sollten Sie Folgendes angeben:

- Einen leicht verständlichen Namen für den Standort des Notfallanrufers, um sicherzustellen, dass Notrufempfänger den Standort unverzüglich auffinden, wenn sie an der durchgegebenen Adresse eintreffen. Dieser Standortname kann die Hausnummer, das Stockwerk, den Gebäudetrakt, die Zimmernummer usw. beinhalten. Vermeiden Sie Spitznamen, die nur Mitarbeiter kennen und dazu führen könnten, dass sich Notrufempfänger zur falschen Adresse begeben.

- Eine Standort-ID, mit der Benutzer leicht erkennen können, dass ihr Skype for Business-Client den richtigen Speicherort ausgewählt hat. Der Skype for Business-Client verkatert automatisch die ermittelten Felder **Location** und **City** in der Kopfzeile und zeigt diese an. Eine bewährte Methode ist das Hinzufügen der Straßenadresse des Gebäudes zu jedem Standortbezeichner (z. B. "1. Stock <street number> "). Ohne die Adresse der Straße könnte ein generischer Standortbezeichner wie "1. Stock" auf jedes Gebäude in der Stadt angewendet werden.

- Wenn der Standort ungefähr ist, da er von einem Drahtlosen Zugriffspunkt bestimmt wird, können Sie das Wort **[Near]** hinzufügen (z. B. "Near 1st Floor 1234").

> [!NOTE]
> Der zentralen Standortdatenbank hinzugefügte Speicherorte stehen dem Client erst zur Verfügung, wenn sie mithilfe eines Skype for Business Server-Verwaltungsshell-Befehls veröffentlicht und in die lokalen Speicher des Pools repliziert werden. Ausführliche Informationen finden Sie unter [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) in der Bereitstellungsdokumentation.

In den folgenden Abschnitten erfahren Sie, was Sie beim Auffüllen und Verwalten der Standortdatenbank bedenken müssen.

## <a name="populating-the-location-database"></a>Auffüllen der Standortdatenbank

Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank aufgefüllt werden soll.

 **Welches Verfahren verwenden Sie zum Auffüllen der Standortdatenbank?**

Wo befinden sich die Daten, und welche Schritte müssen Sie ausführen, um die Daten in das für die Standortdatenbank erforderliche Format zu konvertieren? Werden die Standorte einzeln oder mithilfe einer CSV-Datei per Massenvorgang hinzugefügt?

 **Verfügen Sie über eine Drittanbieterdatenbank, die bereits Standortzuordnungen enthält?**

Mithilfe der Option Sekundärer Standortinformationsdienst zum Herstellen einer Verbindung mit einer Drittanbieterdatenbank können Sie Standorte mithilfe einer Offlineplattform gruppieren und verwalten. Der Vorteil dieses Ansatzes ist, dass Sie Standorte nicht nur Netzwerk-IDs, sondern auch einem Benutzer zuordnen können. Dies bedeutet, dass der Standortinformationsdienst mehrere Adressen, die vom sekundären Standortinformationsdienst stammen, an einen Skype for Business-Client zurückgeben kann. Der Benutzer kann dann den am besten geeigneten Standort wählen.

Für die Integration in den Standortinformationsdienst muss die Drittanbieterdatenbank dem Lync Server Location Request/Response-Schema folgen. Weitere Informationen finden Sie  [unter "[MS-E911WS]: Web Service for E911 Support Protocol Specification"](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd). Ausführliche Informationen zum Bereitstellen eines sekundären Standortinformationsdiensts finden Sie unter Konfigurieren eines sekundären Standortinformationsdiensts [in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zum Auffüllen der Standortdatenbank finden Sie unter [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) in der Bereitstellungsdokumentation.

## <a name="maintaining-the-location-database"></a>Verwalten der Standortdatenbank

Nach dem Auffüllen der Standortdatenbank müssen Sie eine Strategie zum Aktualisieren der Datenbank entwickeln, um Änderungen an der Netzwerkkonfiguration umzusetzen. Die folgenden Fragen helfen Ihnen zu bestimmen, wie die Standortdatenbank verwaltet werden soll.

 **Wie aktualisieren Sie die Standortdatenbank?**

Eine Aktualisierung der Standortdatenbank kann in verschiedenen Situationen notwendig sein, etwa beim Hinzufügen von Funkzugriffspunkten, bei einer Neuverkabelung des Büros (mit neuen Switchzuordnungen) und bei einer Subnetzerweiterung. Aktualisieren Sie jeden Standort sofort, oder führen Sie mithilfe einer CSV-Datei eine Aktualisierung aller Standorte per Massenvorgang durch?

 **Verwenden Sie eine SNMP-Anwendung zum Abgleich von Lync-Client-MAC-Adressen mit den Port- und Switchbezeichnern?**

Wenn Sie eine SNMP-Anwendung verwenden, müssen Sie ein manuelles Verfahren ausarbeiten, um die Konsistenz der Switch- und Portinformationen zwischen der SNMP-Anwendung und der Standortdatenbank sicherzustellen. Wenn die SNMP-Anwendung eine Chassis-IP-Adresse oder Port-ID zurückgibt, die nicht in der Datenbank enthalten ist, kann der Standortinformationsdienst keinen Speicherort an den Client zurückgeben.