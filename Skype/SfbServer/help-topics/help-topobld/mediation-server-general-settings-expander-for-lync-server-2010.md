---
title: Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Sie können die Eigenschaften der Mediation Server in diesem Dialogfeld bearbeiten. Auf der linken Seite ist eine Reihe von Quicklinks zu gelangen Sie zur Einstellungen für allgemeine Einstellungen, die Einstellungen für den nächsten Hop und Einstellungen für PSTN-Gateway. In jedem Abschnitt sind die folgenden Einstellungen:'
ms.openlocfilehash: ed4ed6c1c480417850bbfe194702a04b9e3af75f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888457"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Allgemeine Einstellungen für den Vermittlungsserver für Lync Server 2010 – Erweiterung

Sie können die Eigenschaften der Mediation Server in diesem Dialogfeld bearbeiten. Auf der linken Seite ist eine Reihe von Quicklinks zu gelangen Sie zur Einstellungen für allgemeine Einstellungen, die Einstellungen für den nächsten Hop und Einstellungen für PSTN-Gateway. In jedem Abschnitt sind die folgenden Einstellungen:

 **Allgemein**:

- **FQDN**: Bearbeiten Sie den vollqualifizierten Domänennamen des Vermittlungsservers

- **Zuordnungen**: Aktivieren Sie das Kontrollkästchen **edgepool zuordnen (für Medienkomponenten)** , und wählen Sie eine Edge-Server oder einem Edge-Pools für den Vermittlungsserver als Medienpfad für den externen Zugriff verwendet.

  **Nächster Hop**:

- **Auswahl für nächsten Hop**: den Front-End-Server oder Front-End-Pool als den Pfad für den Vermittlungsserver verwendet werden, um für die Kommunikation mit der Bereitstellung zu verwendende aus einer Liste auswählen.

  **PSTN-Gateway**:

  **Mediation Server PSTN-Gateway**:

- **Überwachungsports**: Definieren Sie die Ports, die der Vermittlungsserver überwacht wird. Sie können einen Port für **TLS** oder Transport Layer Security oder **TCP**, definieren oder transport Control-Protokoll. Für den Porteintrag für TCP verfügbar sein soll müssen Sie das Kontrollkästchen für **Aktivieren TCP-Port**auswählen.

    > [!IMPORTANT]
    > Finden Sie in der Dokumentation und Konfiguration Einstellungen für Ihre Gateway public switched Telephone Network, (PSTN) zu ermitteln, wenn Sie bei aktivierter definieren müssen Port TLS, TCP oder beide Werte. TLS ist eine sicherere Protokoll, Verwendung von Zertifikaten zur Verschlüsselung des Datenverkehrs zwischen dem Vermittlungsserver und PSTN-Gateway. Nicht alle PSTN-Gateways unterstützt TLS.

- Eine Liste der SIP-Trunks und Gateways, die definiert und für Ihre Bereitstellung konfiguriert sind, wird angezeigt. Wenn keine Einträge vorhanden sind, sind keine SIP-Trunks oder PSTN-Gateways für die Bereitstellung konfiguriert. Sie definieren und Konfigurieren von Trunks und **Freigegebene Komponenten** -Gateways im Topologie-Generator.

## <a name="see-also"></a>Siehe auch

[Übersicht über SIP-Trunking](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[Bereitstellungsoptionen für PSTN-Gateway](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
