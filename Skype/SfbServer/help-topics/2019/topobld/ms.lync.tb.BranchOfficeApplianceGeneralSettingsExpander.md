---
title: Allgemeine Einstellungen für Filialanwendungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
ROBOTS: NOINDEX, NOFOLLOW
description: 'Wenn Sie die Einstellungen für eine vorhandene überlebensfähige Branch Appliance oder einen Überlebenden Branch-Server bearbeiten möchten, werden Ihnen die folgenden Abschnitte angezeigt:'
ms.openlocfilehash: bcd1022c964a252ca08d4a8c000b224f61c42763
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294299"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Allgemeine Einstellungen für Filialanwendungen – Erweiterung

Wenn Sie die Einstellungen für eine vorhandene überlebensfähige Branch Appliance oder einen Überlebenden Branch-Server bearbeiten möchten, werden Ihnen die folgenden Abschnitte angezeigt:

- Allgemeine Einstellungen

- Flexibilitätseinstellungen

- Vermittlungsservereinstellungen


Bei einer Survivable Branch-Appliance oder einem Überlebenden Branch-Server wird Folgendes angezeigt:

### <a name="general-settings"></a>Allgemeine Einstellungen

Den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Survivable Branch Appliance oder des Survivable Branch-Servers. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.

Sie können die Option **Alle konfigurierten IP-Adressen verwenden** oder **Dienstnutzung auf ausgewählte IP-Adressen beschränken** wählen. Wenn Sie die Option **Dienst auf definierte IP-Adressen beschränken** wählen, definieren Sie die primäre IP-Adresse, die der Server für die gesamte Kommunikation verwendet (mit Ausnahme der PSTN-Kommunikation). Für die Verwendung mit dem Telefonfestnetz wird eine gesonderte IP-Adresse bestimmt.

In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:

- Mit dem Zuordnen des Archivierungsservers können Sie auswählen, ob Sie einen Archivierungsserver mit der Survivable Branch Appliance oder einem Survivable Branch-Server verknüpfen möchten. Sie können einen bereits definierten Archivierungsserver auswählen, indem Sie den Server aus der Dropdownliste auswählen oder auf **neu** klicken, um einen neuen Archivierungsserver anzugeben.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

- Mit dem Associate Monitoring Server können Sie auswählen, ob Sie einen Überwachungsserver mit der Survivable Branch Appliance oder einem Survivable Branch-Server verknüpfen möchten. Sie können einen bereits definierten Überwachungsserver auswählen, indem Sie den Server aus der Dropdownliste auswählen oder auf **neu** klicken, um einen neuen Überwachungsserver anzugeben.

- Mit dem Zuordnen eines Edge-Pools können Sie auswählen, ob Sie einen Edgeserver oder Pool mit der Survivable Branch Appliance oder einem Survivable Branch-Server verknüpfen möchten. Sie können in der Dropdownliste einen bereits definierten Edgeserver oder -pool auswählen oder auf **Neu** klicken, um einen neuen Edgeserver oder -pool anzugeben.

### <a name="resiliency"></a>Flexibilität

Dank der Flexibilität (Ausfallsicherheit) ist die hohe Verfügbarkeit des Registrierungspools gewährleistet. Durch Bereitstellung einer Sicherungsregistrierungsstelle für den Fall eines Ausfalls der primären Registrierungsstelle kann die Sicherungsregistrierungsstelle die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann es, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, möglicherweise zu einer eingeschränkten Funktionalität kommen.

Wählen Sie in der Dropdownliste den Enterprise Edition-Front-End-Pool oder den Standard Edition-Front-End-Server aus, der als Sicherungs Registrierungsstelle für die Survivable Branch Appliance oder den Survivable Branch-Server fungieren soll. Sie können außerdem Zeitintervalle für Failover und Fallback auswählen. Die (in Sekunden angegebenen) Zeiteinstellungen für Failover und Fallback ermöglichen die automatische Erkennung einer ausgefallenen Registrierung und eines Zeitpuffers zur automatischen Bestimmung, dass die primäre Registrierung wieder betriebsbereit ist und den Registrierungsprozess übernehmen kann.

> [!IMPORTANT]
> Achten Sie beim Definieren der Fehlererkennung und des Fall Back Intervalls darauf, dass kein Intervall eingegeben wird, bei dem Failover und Fallback auftreten, wenn die Registrierungsstelle für einen kurzen Zeitraum nicht antwortet. Es ist möglich, dass die primäre Registrierungsstelle aufgrund des Ladens des Pools oder der Server für kurze Zeiträume nicht reagiert. Die Standardwerte für eine Survivable Branch-Appliance oder einen Survivable-Branch-Server auf einer Website zu einem Pool-oder Standard Edition-Front-End-Server sind 120 Sekunden für Failover und 240 Sekunden für Fallback.

### <a name="mediation-server"></a>Vermittlungsserver

Für **Vermittlungsserver** können Sie Folgendes angeben:

Das Kontrollkästchen für den **aktivierten Mediationsserver** steht auf einer Survivable Branch-Appliance oder einem Überlebenden Branch-Server nicht zur Verfügung, da sich der Vermittlungsserver befindet.

Sie definieren den Abhör Port auf den Pool Servern für TLS (Transport Layer Security). Standardmäßig ist dieser Port 5067. Wenn Sie **TCP-Port aktivieren**auswählen, müssen Sie einen TCP-Port für den beiliegenden Vermittlungs Server definieren. Hierbei handelt es sich um eine optionale Einstellung, und Sie sollten sich auf die Anforderungen Ihrer Gateway-oder PSTN-Anforderungen beziehen, um festzustellen, ob dies erforderlich ist. Standardmäßig ist der TCP-Port-Wert 5068.

Sie definieren PSTN-Gateways, die dem zusammengefassten Vermittlungs Server zugeordnet sind. Wenn Sie bereits Gateways definiert haben, stehen diese dem Vermittlungs Server zur Verfügung. Falls noch keine Gateways definiert wurden, jedoch zur Definition zur Verfügung stehen, können Sie **Neu** auswählen. Sie können auch Gateways entfernen, die bereits für diesen Vermittlungs Server konfiguriert sind. Wählen Sie das Gateway aus, und klicken Sie dann auf **Entfernen**.

Wenn einem Vermittlungs Server mehr als ein Gateway zugeordnet ist, ist das erste zugeordnete Gateway das Standardgateway. Wenn Sie ein anderes Gateway als Standardgateway auswählen müssen, wählen Sie das gewünschte Gateway aus, und klicken Sie auf **Als Standard**.


Details zum Definieren und Konfigurieren der Einstellungen für die Survivable Branch Appliance oder den Survivable Branch-Server finden Sie unter Lösungen für die [Stabilität von Zweig](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)stellen.


