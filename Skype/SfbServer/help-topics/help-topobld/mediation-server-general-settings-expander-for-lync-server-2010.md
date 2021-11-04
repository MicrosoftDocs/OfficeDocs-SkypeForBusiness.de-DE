---
title: Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Vermittlungsserver. Auf der linken Seite befinden sich mehrere direkte Links zu den Einstellungen unter "Allgemein", "Einstellungen für nächsten Hop" und "Einstellungen für PSTN-Gateway". In jedem Abschnitt sind die folgenden Einstellungen enthalten:'
ms.openlocfilehash: fe582895da29e1421ee4e605c84831991bef809a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743652"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung

In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Vermittlungsserver. Auf der linken Seite befinden sich mehrere direkte Links zu den Einstellungen unter "Allgemein", "Einstellungen für nächsten Hop" und "Einstellungen für PSTN-Gateway". In jedem Abschnitt sind die folgenden Einstellungen enthalten:

 **Allgemein:**

- **FQDN:** Sie bearbeiten den vollqualifizierten Domänennamen des Vermittlungsservers.

- **Zuordnungen:** Aktivieren Sie das Kontrollkästchen **"Edgepool zuordnen" (für Medienkomponenten),** und wählen Sie einen Edgeserver oder Edgepool für den Vermittlungsserver aus, der als Medienpfad für den externen Zugriff verwendet werden soll.

  **Nächster Hop**:

- **Next hop selection:** Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.

  **PSTN-Gateway**:

  **PSTN-Gateway für Vermittlungsserver**:

- **Überwachungsports:** Definieren Sie die Ports, auf die der Vermittlungsserver lauscht. Sie können einen Port für **TLS** (Transport Layer Security) oder **TCP** (Transport Control Protocol) definieren. Damit der Porteintrag für TCP verfügbar ist, müssen Sie das Kontrollkästchen **TCP-Port aktivieren** aktivieren.

    > [!IMPORTANT]
    > Ermitteln Sie anhand der Dokumentation und Konfigurationseinstellungen für das PSTN-Gateway (Public Switched Telephone Network), ob Sie Portwerte für TLS, TCP oder beides aktivieren und definieren müssen. TLS ist ein sichereres Protokoll, bei dem Zertifikate zum Verschlüsseln des Datenverkehrs zwischen dem Vermittlungsserver und dem PSTN-Gateway verwendet werden. Nicht alle PSTN-Gateways unterstützen TLS.

- Es ist eine Liste mit SIP-Trunks und den Gateways angegeben, die für die Bereitstellung definiert und konfiguriert sind. Falls keine Einträge vorhanden sind, sind für die Bereitstellung keine SIP-Trunks oder PSTN-Gateways konfiguriert. Sie definieren und konfigurieren Trunks und Gateways unter **"Freigegebene Komponenten"** im Topologie-Generator.

## <a name="see-also"></a>Weitere Informationen

[Übersicht über SIP-Trunking](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[Bereitstellungsoptionen für PSTN-Gateways](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)