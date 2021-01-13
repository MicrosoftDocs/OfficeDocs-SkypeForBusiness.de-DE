---
title: Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
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
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Vermittlungsserver. Auf der linken Seite befinden sich mehrere direkte Links zu den Einstellungen unter "Allgemein", "Einstellungen für nächsten Hop" und "Einstellungen für PSTN-Gateway". In jedem Abschnitt sind die folgenden Einstellungen enthalten:'
ms.openlocfilehash: db7964826a50f462435769d66ddfab3804462541
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806745"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung

In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Vermittlungsserver. Auf der linken Seite befinden sich mehrere direkte Links zu den Einstellungen unter "Allgemein", "Einstellungen für nächsten Hop" und "Einstellungen für PSTN-Gateway". In jedem Abschnitt sind die folgenden Einstellungen enthalten:

 **Allgemein:**

- **FQDN:** Sie bearbeiten den vollqualifizierten Domänennamen des Vermittlungsservers

- **Zuordnungen:** Aktivieren Sie das Kontrollkästchen **"Edgepool zuordnen" (für Medienkomponenten),** und wählen Sie einen Edgeserver oder Edgepool für den Vermittlungsserver aus, der als Medienpfad für den externen Zugriff verwendet werden soll.

  **Nächster Hop**:

- **Auswahl des nächsten** Hops: Wählen Sie in einer Liste den Front-End-Server oder Front-End-Pool aus, der als Pfad für den Vermittlungsserver für die Kommunikation mit Ihrer Bereitstellung verwendet werden soll.

  **PSTN-Gateway**:

  **PSTN-Gateway für Vermittlungsserver**:

- **Abhörports:** Definieren Sie die Ports, die der Vermittlungsserver abhört. Sie können einen Port für **TLS** (Transport Layer Security) oder **TCP** (Transport Control Protocol) definieren. Damit der Porteintrag für TCP verfügbar ist, müssen Sie das Kontrollkästchen **TCP-Port aktivieren** aktivieren.

    > [!IMPORTANT]
    > Ermitteln Sie anhand der Dokumentation und Konfigurationseinstellungen für das PSTN-Gateway (Public Switched Telephone Network), ob Sie Portwerte für TLS, TCP oder beides aktivieren und definieren müssen. TLS ist ein sichereres Protokoll, das Zertifikate verwendet, um den Datenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway zu verschlüsseln. Nicht alle PSTN-Gateways unterstützen TLS.

- Es ist eine Liste mit SIP-Trunks und den Gateways angegeben, die für die Bereitstellung definiert und konfiguriert sind. Falls keine Einträge vorhanden sind, sind für die Bereitstellung keine SIP-Trunks oder PSTN-Gateways konfiguriert. Sie definieren und konfigurieren Trunks und Gateways unter **"Freigegebene Komponenten"** im Topologie-Generator.

## <a name="see-also"></a>Siehe auch

[Übersicht über SIP-Trunking](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Bereitstellungsoptionen für PSTN-Gateways](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
