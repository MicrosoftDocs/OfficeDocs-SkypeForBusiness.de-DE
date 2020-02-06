---
title: Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Vermittlungsserver. Auf der linken Seite finden Sie eine Reihe von schnell Links, die Sie zu den Einstellungen für allgemeine Einstellungen, Einstellungen für den nächsten Hop und Einstellungen für das PSTN-Gateway führen. In jedem Abschnitt sind die folgenden Einstellungen zu finden:'
ms.openlocfilehash: 3f7dad61778f54fee7a9be984191bc21f5029502
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819617"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung

In diesem Dialogfeld bearbeiten Sie die Eigenschaften der Vermittlungsserver. Auf der linken Seite finden Sie eine Reihe von schnell Links, die Sie zu den Einstellungen für allgemeine Einstellungen, Einstellungen für den nächsten Hop und Einstellungen für das PSTN-Gateway führen. In jedem Abschnitt sind die folgenden Einstellungen zu finden:

 **Allgemein**:

- **FQDN**: Sie bearbeiten den vollqualifizierten Domänennamen des Vermittlungsservers.

- **Zuordnungen**: Aktivieren Sie das Kontrollkästchen **Edge-Pool zuordnen (für Medienkomponenten)** , und wählen Sie einen Edgeserver oder einen Edge-Pool aus, den der Vermittlungsserver als Medienpfad für den externen Zugriff verwenden soll.

  **Nächster Hop**:

- **Auswahl für den nächsten Hop**: Wählen Sie in einer Liste den Front-End-Server oder den Front-End-Pool aus, der als Pfad für den Vermittlungsserver für die Kommunikation mit Ihrer Bereitstellung verwendet werden soll.

  **PSTN-Gateway**:

  **Vermittlungs Server-PSTN-Gateway**:

- **Abhör Anschlüsse**: definieren Sie die Ports, die vom Vermittlungs Server überwacht werden. Sie können einen Port für **TLS** oder Transport Layer Security oder **TCP**oder Transport Control Protocol definieren. Damit der Port Eintrag für TCP verfügbar ist, müssen Sie das Kontrollkästchen für TCP- **Port aktivieren**aktivieren.

    > [!IMPORTANT]
    > Informationen dazu finden Sie in den Dokumentations-und Konfigurationseinstellungen für das PSTN-Gateway (Public Switched Telephone Network), um festzustellen, ob Portwerte TLS, TCP oder beides aktiviert und definiert werden müssen. TLS ist ein sichereres Protokoll, in dem der Datenverkehr zwischen dem Vermittlungs Server und dem PSTN-Gateway mithilfe von Zertifikaten verschlüsselt wird. Nicht alle PSTN-Gateways unterstützen TLS.

- Eine Liste der SIP-Trunks und der Gateways, die für Ihre Bereitstellung definiert und konfiguriert sind, wird aufgelistet. Wenn keine Einträge vorhanden sind, gibt es keine SIP-Trunks oder PSTN-Gateways, die für Ihre Bereitstellung konfiguriert sind. Sie definieren und konfigurieren Trunks und Gateways unter **freigegebene Komponenten** im Topologie-Generator.

## <a name="see-also"></a>Siehe auch

[Übersicht über SIP-Trunking](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Bereitstellungsoptionen für PSTN-Gateways](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
