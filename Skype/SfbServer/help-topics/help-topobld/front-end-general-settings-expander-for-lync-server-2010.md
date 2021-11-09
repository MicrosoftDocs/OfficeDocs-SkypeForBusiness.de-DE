---
title: Allgemeine Einstellungen für das Front-End für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Sie bearbeiten die Eigenschaften des Front-End-Servers oder Front-End-Pools, indem Sie die folgenden Attribute bearbeiten oder konfigurieren. Die Konfigurationsseite ist in die folgenden Abschnitte unterteilt:'
ms.openlocfilehash: b515acd1aa475247f0f87206a0af50eedb21a294
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855562"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Allgemeine Einstellungen für das Front-End für Lync Server 2010 – Erweiterung

Sie bearbeiten die Eigenschaften des Front-End-Servers oder Front-End-Pools, indem Sie die folgenden Attribute bearbeiten oder konfigurieren. Die Konfigurationsseite ist in die folgenden Abschnitte unterteilt:

 **Allgemein**

- **FQDN:** Der vollqualifizierte Domänenname des Front-End-Servers oder Front-End-Pools.

- Wählen Sie **"Alle konfigurierten IP-Adressen verwenden"** aus, um alle Auf dem Front-End-Server oder Front-End-Pool konfigurierten Adressen zu verwenden.

    > [!IMPORTANT]
    > Sie sollten diese Option nicht auswählen, wenn Sie den Vermittlungsserver auf dem Front-End-Server oder Front-End-Pool verbinden. Vermittlungsserver und Front-End-Server benötigen dedizierte IP-Adressen für die Kommunikation.

- Wählen Sie **"Dienstnutzung auf ausgewählte IP-Adressen beschränken"** aus, und geben Sie die IP-Adresse für die **primäre IP-Adresse** für den Front-End-Server oder die Kommunikation mit dem Front-End-Pool mit dem Rest der Bereitstellung ein. Geben Sie in der **PSTN-IP-Adresse** die IP-Adresse ein, die dem Vermittlungsserver zugeordnet ist.

    **Funktionen und Funktionalität**

- **Konferenzen**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie in der Bereitstellung Konferenzfunktionen verwenden möchten. Konferenzen verfügen über Funktionen wie Audio, Video, Anwendungsfreigabe, Desktopfreigabe und Webkonferenzen. Sie müssen einen Office Web Apps-Server für Webkonferenzen erstellen und zuordnen (später auf dieser Eigenschaftenseite definiert).

- Wenn Sie die Option "Konferenzen" ausgewählt haben, können Sie **Einwahlkonferenzen (PSTN)** verwenden. Aktivieren Sie das Kontrollkästchen, um die Verwendung der Funktionen für Einwahlkonferenzen zu ermöglichen.

- Aktivieren Sie das Kontrollkästchen **Enterprise-VoIP,** wenn Sie Features bereitstellen möchten, mit denen Lync Server 2013 als Telefontelefonsystem mit VoIP-Technologien (Voice over IP) fungiert, einschließlich der Option, Telefone, SIP-Trunks oder Netzwerkverbindungen mit öffentlichen Telefonen mithilfe von Vermittlungsservern, PSTN-Gateways und IP-Nebenstellenanlagen in Kombination oder allein bereitzustellen.  basierend auf dem Entwurf und den Anforderungen. Ausführliche Informationen zu Enterprise-VoIP finden Sie unter [Enterprise-VoIP](/previous-versions/office/lync-server-2013/lync-server-2013-enterprise-voice) und [Plan for Enterprise-VoIP in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Verbände**

- **SQL Server Speicher:** Der FQDN des SQL Server (und optional eine benannte Instanz), die dem Front-End-Server oder Front-End-Pool zugeordnet ist. Sie wählen den SQL Server-Speicher aus der Liste aus oder erstellen eine neue SQL Server-Instanz, indem Sie auf **Neu** klicken.

- **Dateispeicher:** Sie wählen den FQDN des Servers und die Freigabe (im Format) aus, die  `\\<FQDN of server>\<share name>` als Speicherort für den Dateispeicher für die freigegebenen Dateien fungiert, die Lync Server 2013 für Replikation, Konferenzverzeichnisse und andere Zwecke erstellt und verwendet. Sie wählen den Dateispeicher in der Liste aus oder erstellen einen neuen Dateispeicher, indem Sie auf **Neu** klicken.

- Aktivieren Sie das Kontrollkästchen **Archivierungsserver zuordnen,** um einen Archivierungsserver für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nachdem Sie das Kontrollkästchen aktiviert haben, wählen Sie einen vorhandenen Archivierungsserver aus der Liste aus, oder klicken Sie auf **Neu,** um die Definitionen für einen neuen Archivierungsserver zu erstellen.

- Aktivieren Sie das Kontrollkästchen **"Monitoring Server zuordnen",** um einen Überwachungsserver für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nachdem Sie das Kontrollkästchen aktiviert haben, wählen Sie einen vorhandenen Monitoring Server aus der Liste aus, oder klicken Sie auf **Neu,** um die Definitionen für einen neuen Monitoring Server zu erstellen.

- Aktivieren Sie das Kontrollkästchen **"Edgepool zuordnen" (Kontrollkästchen für Medienkomponenten,** um einen Edgeserver für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nachdem Sie das Kontrollkästchen aktiviert haben, wählen Sie einen vorhandenen Edgeserver oder -pool aus der Liste aus, oder klicken Sie auf **Neu,** um die Definitionen für einen neuen Edgeserver oder -pool zu erstellen.

  **Ausfallsicherheit**

- Aktivieren Sie das Kontrollkästchen **"Zugeordneter Sicherungsregistrierungspool",** um in der Liste einen Front-End-Server oder Front-End-Pool auszuwählen, bei dem es sich um die Sicherungsregistrierungsstelle handelt (d. b. den Front-End-Server oder den Front-End-Pool, der als sekundäre Registrierungsstelle für den Fall festgelegt ist, dass die primäre Registrierung fehlschlägt).

- Wenn Sie die Option "Zugeordneter Sicherungsregistrierungsstellen-Pool" und eine Sicherungsregistrierungsstelle ausgewählt haben, können Sie das Kontrollkästchen der Option **Automatisches Failover und Failback für Sprachdienste** aktivieren. Danach können Sie numerische Eigenschaften für **Erkennungsintervall für Sprachdienstfehler (Sek.)** und **Failbackintervall für Sprache (Sek.)** definieren. Ausführliche Informationen finden Sie unter [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency).

  **Webdienste**

- Zum Konfigurieren von **Interne Webdienste** definieren Sie **Überwachungsports** für **HTTP** und **HTTPS**. Standardmäßig sind dies TCP-Port 80 bzw. TCP-Port 443. Sie können auch die Option **Veröffentlichte Ports** für **HTTP** und **HTTPS** konfigurieren. Standardmäßig sind dies TCP-Port 80 bzw. TCP-Port 443. Passen Sie die Portwerte basierend auf der Konfiguration der internen Webdienste und Verwendung des Lastenausgleichs (Hardwarelastenausgleich und DNS-Lastenausgleich) an, um die Überwachungsports und veröffentlichten Ports zu definieren.

    > [!IMPORTANT]
    > Interne Webdienste und die definierten Überwachungsports und veröffentlichten Ports gelten für interne Clients und Geräte. Für externe Clients und Geräte werden die Überwachungsports und veröffentlichten Ports der externen Webdienste in Verbindung mit dem definierten vollqualifizierten Domänennamen (FQDN) der externen Webdienste verwendet.

- Zum Konfigurieren von **Externe Webdienste** definieren Sie **Überwachungsports** für **HTTP** und **HTTPS**. Standardmäßig sind dies TCP-Port 80 bzw. TCP-Port 443. Sie können auch die Option **Veröffentlichte Ports** für **HTTP** und **HTTPS** konfigurieren. Standardmäßig sind dies TCP-Port 80 bzw. TCP-Port 443. Passen Sie die Portwerte basierend auf der Konfiguration der internen Webdienste und Verwendung des Lastenausgleichs (Hardwarelastenausgleich und DNS-Lastenausgleich) an, um die Überwachungsports und veröffentlichten Ports zu definieren.

    > [!IMPORTANT]
    > Externe Webdienste und die definierten Überwachungsports und veröffentlichten Ports gelten für externe Clients und Geräte. Für externe Clients und Geräte werden die Überwachungsports und veröffentlichten Ports der externen Webdienste (normalerweise vom Reverseproxy definiert) in Verbindung mit dem definierten vollqualifizierten Domänennamen (FQDN) der externen Webdienste verwendet. Die Beziehung des FQDN der externen Webdienste und von Einfache URLs definiert die URL-Adressen (Uniform Resource Locator), die von externen Clients zum Zugreifen auf die für externe Besucher und Geräte verfügbaren Dienste verwendet werden. Ausführliche Informationen zu einfachen URLs finden Sie unter [Planning for Simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls).

  **Vermittlungsserver**

- Wählen Sie zum Konfigurieren der **Vermittlungsservereigenschaften** für einen verbundenen Vermittlungsserver (d. h. einen Vermittlungsserver, der auf dem Front-End-Server oder Front-End-Pool bereitgestellt wird) die **Option "Verbundener Vermittlungsserver" aus.**

- Um die **Überwachungsports** für einen verbundenen Vermittlungsserver zu definieren, geben Sie den **TLS-** und **TCP-Portwert** ein, auf den der verbundenen Vermittlungsserver lauscht. Standardmäßig ist TLS als TCP-Port 5067 definiert.

- Um einen TCP-Portwert für den Vermittlungsserver zu definieren, aktivieren Sie das Kontrollkästchen **TCP-Port aktivieren.** Standardmäßig verwendet der Vermittlungsserver die Transport Layer Security (TLS) über das TCP-Protokoll. TCP-Ports sind nur verfügbar, wenn die Option "TCP-Port aktivieren" aktiviert ist.

    > [!NOTE]
    > Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.

- Sie definieren Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

    Wenn einem Vermittlungsserver mehrere Gateways zugeordnet sind, können Sie das Standardgateway angeben, indem Sie das Gateway auswählen, das Sie als Standard festlegen möchten, und auf **"Als Standard festlegen"** klicken. Falls Sie das aktuelle Standardgateway entfernen möchten, wählen Sie das Gateway aus und klicken auf **Festlegung als Standardeinstellung aufheben**.

> [!IMPORTANT]
> Wenn Sie in diesem Dialogfeld Änderungen an den Eigenschaften vornehmen, müssen Sie die Topologie veröffentlichen und den Skype for Business Server Bereitstellungs-Assistenten auf allen betroffenen Servern ausführen. Nach der Veröffentlichung der neuen Topologie wird eine Liste der betroffenen Server, auf denen der Skype for Business Server Bereitstellungs-Assistent ausgeführt werden muss, als Link auf dem Zusammenfassungsbildschirm für die erfolgreiche Topologieveröffentlichung bereitgestellt. Ausführliche Informationen zur Veröffentlichung der aktualisierten Topologie finden Sie unter [Publish the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-topology). Ausführliche Informationen zum Bereitstellungs-Assistenten für Skype for Business Server finden Sie unter [Lync Server-Verwaltungstools.](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-administrative-tools)

Klicken Sie auf **OK**, um die Änderungen des Topologiedokuments zu speichern und zu übernehmen.

Klicken Sie auf **"Abbrechen",** um die Änderungen zu verwerfen und die **Bearbeitungseigenschaften** für den Front-End-Server oder Front-End-Pool zu schließen.

Klicken Sie auf **Hilfe**, um dieses Hilfethema anzuzeigen.

## <a name="see-also"></a>Siehe auch

[Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)