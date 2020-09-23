---
title: Allgemeine Einstellungen für Branch Office Appliance – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Die Einstellungen für eine vorhandene Survivable Branch Appliance oder einen Survivable Branch Server werden in den folgenden Abschnitten bearbeitet:'
ms.openlocfilehash: 40ebf4a22bcfc3392c2f1dc8238a46b610d22281
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216126"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Allgemeine Einstellungen für Branch Office Appliance – Erweiterung

Die Einstellungen für eine vorhandene Survivable Branch Appliance oder einen Survivable Branch Server werden in den folgenden Abschnitten bearbeitet:

- Allgemeine Einstellungen

- Flexibilitätseinstellungen

- Vermittlungsservereinstellungen



Für eine Survivable Branch Appliance oder einen Survivable Branch Server wird Folgendes angezeigt:

## <a name="general-settings"></a>Allgemeine Einstellungen

Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) der Survivable Branch Appliance oder des Survivable Branch Servers. Bearbeiten Sie den FQDN des Servers, um den Wert zu ändern. Sie müssen über einen DNS-A-Eintrag (Domain Name System) verfügen, der mit dem neuen Wert übereinstimmt.

Sie können die Option **Alle konfigurierten IP-Adressen verwenden** oder **Dienstnutzung auf ausgewählte IP-Adressen beschränken** wählen. Wenn Sie den Dienst auf definierte IP-Adressen beschränken, definieren Sie die primäre IP-Adresse, die der Server für die gesamte Kommunikation verwendet (mit Ausnahme der PSTN-Kommunikation).**** Für die Verwendung mit dem Telefonfestnetz wird eine gesonderte IP-Adresse bestimmt.

In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:

- Mit zuordnen Archivierungsserver können Sie auswählen, ob ein Archivierungsserver dem Survivable Branch Appliance oder Survivable Branch Server zugeordnet werden soll. Sie können ein bereits definiertes Archivierungsserver auswählen, indem Sie den Server aus der Dropdownliste auswählen oder auf **neu** klicken, um einen neuen Archivierungsserver anzugeben.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

- Mit zuordnen Monitoring Server können Sie auswählen, ob ein Monitoring Server dem Survivable Branch Appliance oder Survivable Branch Server zugeordnet werden soll. Sie können ein bereits definiertes Monitoring Server auswählen, indem Sie den Server aus der Dropdownliste auswählen oder auf **neu** klicken, um einen neuen Monitoring Server anzugeben.

- Mit Associate Edgepool können Sie auswählen, ob eine Edgeserver oder ein Pool dem Survivable Branch Appliance oder Survivable Branch Server zugeordnet werden soll. Sie können in der Dropdownliste einen bereits definierten Edgeserver oder -pool auswählen oder auf **Neu** klicken, um einen neuen Edgeserver oder -pool anzugeben.

## <a name="resiliency"></a>Flexibilität

Dank der Flexibilität (Ausfallsicherheit) ist die hohe Verfügbarkeit des Registrierungspools gewährleistet. Durch Bereitstellung einer Sicherungsregistrierungsstelle für den Fall eines Ausfalls der primären Registrierungsstelle kann die Sicherungsregistrierungsstelle die Aufgabe der ausgefallenen Registrierung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann es, je nachdem, welche Systeme mit der primären Registrierung ausgefallen sind, möglicherweise zu einer eingeschränkten Funktionalität kommen.

Wählen Sie in der Dropdownliste die Enterprise Edition-Front-End-Pool oder Standard Edition-Front-End-Server aus, die als Sicherungs Registrierungsstelle für die Survivable Branch Appliance oder Survivable Branch Server fungieren soll. Sie können außerdem Zeitintervalle für Failover und Fallback auswählen. Die (in Sekunden angegebenen) Zeiteinstellungen für Failover und Fallback ermöglichen die automatische Erkennung einer ausgefallenen Registrierung und eines Zeitpuffers zur automatischen Bestimmung, dass die primäre Registrierung wieder betriebsbereit ist und den Registrierungsprozess übernehmen kann.

> [!IMPORTANT]
> Achten Sie beim Definieren der Fehlererkennung und des Fallback-Intervalls darauf, kein Intervall einzugeben, das dazu führt, dass Failover und Fallback auftreten, wenn die Registrierungsstelle für einen kurzen Zeitraum nicht antwortet. Möglicherweise reagiert die primäre Registrierungsstelle aufgrund des Ladens des Pools oder der Server nicht für kurze Zeiträume. Die Standardwerte für ein Survivable Branch Appliance oder ein Survivable Branch Server in einer Website zu einem Pool oder Standard Edition Front-End-Server beträgt 120 Sekunden für Failover und 240 Sekunden für Fallback.

## <a name="mediation-server"></a>Vermittlungsserver

Für **Vermittlungsserver** können Sie Folgendes angeben:

Das Kontrollkästchen **Gemeinsam ausgeführter Vermittlungsserver aktiviert** steht für eine Survivable Branch Appliance oder einen Survivable Branch Server nicht zur Verfügung, da der Vermittlungsserver gemeinsam ausgeführt wird.

Für TLS (Transport Layer Security) legen Sie den Überwachungsport für die Poolserver fest. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den gemeinsam ausgeführten Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.

Sie definieren PSTN-Gateways, die dem gemeinsam ausgeführten Vermittlungsserver zugeordnet sind. Wenn bereits Gateways definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung. Falls noch keine Gateways definiert wurden, jedoch zur Definition zur Verfügung stehen, können Sie **Neu** auswählen. Sie können bereits für den jeweiligen Vermittlungsserver konfigurierte Gateways auch entfernen. Wählen Sie das Gateway aus, und klicken Sie dann auf **Entfernen**.

Wenn einem Vermittlungsserver mehrere Gateways zugeordnet sind, ist das erste zugeordnete Gateway das Standardgateway. Wenn Sie ein anderes Gateway als Standardgateway auswählen müssen, wählen Sie das gewünschte Gateway aus, und klicken Sie auf **Als Standard**.

## <a name="see-also"></a>Siehe auch

Weitere Informationen zum Definieren und Konfigurieren der Einstellungen für die Survivable Branch Appliance oder den Survivable Branch Server finden Sie unter [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).


