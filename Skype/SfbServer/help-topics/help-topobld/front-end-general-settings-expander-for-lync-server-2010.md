---
title: Allgemeine Einstellungen für das Front-End für Lync Server 2010 – Erweiterung
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
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Sie bearbeiten die Eigenschaften des Front-End-Servers oder Front-End-Pools, indem Sie die folgenden Attribute bearbeiten oder konfigurieren. Die Konfigurationsseite ist in die folgenden Abschnitte unterteilt:'
ms.openlocfilehash: 8616d65a73f1fb618a72ab41bc628527aa6e2a59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818395"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Allgemeine Einstellungen für das Front-End für Lync Server 2010 – Erweiterung

Sie bearbeiten die Eigenschaften des Front-End-Servers oder Front-End-Pools, indem Sie die folgenden Attribute bearbeiten oder konfigurieren. Die Konfigurationsseite ist in die folgenden Abschnitte unterteilt:

 **Allgemein**

- **FQDN:** Der vollqualifizierte Domänenname des Front-End-Servers oder Front-End-Pools.

- Wählen **Sie "Alle konfigurierten IP-Adressen verwenden"** aus, um alle Adressen zu verwenden, die auf dem Front-End-Server oder Front-End-Pool konfiguriert sind.

    > [!IMPORTANT]
    > Sie sollten diese Option nicht auswählen, wenn Sie den Vermittlungsserver auf dem Front-End-Server oder Front-End-Pool verbinden. Vermittlungsserver und Front-End-Server benötigen dedizierte IP-Adressen für die Kommunikation.

- Wählen Sie "Dienstnutzung auf ausgewählte **IP-Adressen beschränken"** aus, und geben Sie die IP-Adresse für die primäre IP-Adresse für die Kommunikation des Front-End-Servers oder front-End-Pools mit der restlichen Bereitstellung ein.  Geben Sie die DEM Vermittlungsserver zugeordnete **PSTN-IP-Adresse** ein.

    **Funktionen und Funktionalität**

- **Konferenzen**: Aktivieren Sie dieses Kontrollkästchen, wenn Sie in der Bereitstellung Konferenzfunktionen verwenden möchten. Konferenzen verfügen über Funktionen wie Audio, Video, Anwendungsfreigabe, Desktopfreigabe und Webkonferenzen. Sie müssen einen Office Web Apps Server für Webkonferenzen erstellen und zuordnen (der später auf dieser Eigenschaftenseite definiert wird).

- Wenn Sie die Option "Konferenzen" ausgewählt haben, können Sie **Einwahlkonferenzen (PSTN)** verwenden. Aktivieren Sie das Kontrollkästchen, um die Verwendung der Funktionen für Einwahlkonferenzen zu ermöglichen.

- Aktivieren Sie das Kontrollkästchen **Enterprise-VoIP,** wenn Sie Features bereitstellen möchten, damit Lync Server 2013 mithilfe von Voice over IP (VoIP)-Technologien als Telefontelefonsystem fungieren kann, einschließlich der Option zum Bereitstellen von Telefonen, SIP-Trunks oder Verbindungen mit öffentlichen Telefonnetzen mithilfe von Vermittlungsservern, PSTN-Gateways und IP-PBX, je nach Entwurf und Anforderungen in Kombination oder allein. Weitere Informationen zu Enterprise-VoIP finden Sie unter [Enterprise-VoIP](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) und [Plan for Enterprise-VoIP in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Zuordnungen**

- **SQL Server:** Der FQDN der SQL Server (und optional eine benannte Instanz), die dem Front-End-Server oder Front-End-Pool zugeordnet ist. Sie wählen den SQL Server-Speicher aus der Liste aus oder erstellen eine neue SQL Server-Instanz, indem Sie auf **Neu** klicken.

- **Dateispeicher:** Sie wählen den FQDN des Servers und die Freigabe (im Format) aus, die als Dateispeicherort für die freigegebenen Dateien fungieren, die Lync Server 2013 für Replikation, Konferenzverzeichnissen und andere Zwecke erstellt und  `\\<FQDN of server>\<share name>` verwendet. Sie wählen den Dateispeicher in der Liste aus oder erstellen einen neuen Dateispeicher, indem Sie auf **Neu** klicken.

- Aktivieren Sie **das Kontrollkästchen Archivierungsserver** zuordnen, um einen Archivierungsserver für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nachdem Sie das Kontrollkästchen ausgewählt haben, wählen Sie  in der Liste einen vorhandenen Archivierungsserver aus, oder klicken Sie auf "Neu", um die Definitionen für einen neuen Archivierungsserver zu erstellen.

- Aktivieren Sie **das Kontrollkästchen Monitoring Server zuordnen,** um einen Monitoring Server für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nachdem Sie das Kontrollkästchen ausgewählt haben, wählen Sie  in der Liste einen vorhandenen Monitoring Server aus, oder klicken Sie auf "Neu", um die Definitionen für einen neuen Monitoring Server zu erstellen.

- Aktivieren Sie **das Kontrollkästchen "Edgepool zuordnen" (für Medienkomponenten),** um einen Edgeserver für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nachdem Sie das Kontrollkästchen ausgewählt haben, wählen Sie in  der Liste einen vorhandenen Edgeserver oder -pool aus, oder klicken Sie auf "Neu", um die Definitionen für einen neuen Edgeserver oder -pool zu erstellen.

  **Resilienz**

- Aktivieren  Sie das Kontrollkästchen zugeordneter Sicherungsregistrierungspool, um in der Liste einen Front-End-Server oder Front-End-Pool auszuwählen, der als Sicherungsregistrierungsstelle festgelegt wird (d. h. der Front-End-Server oder Front-End-Pool, der im Falle eines Ausfalls des primären Servers als sekundäre Registrierungsstelle festgelegt wurde)

- Wenn Sie die Option "Zugeordneter Sicherungsregistrierungsstellen-Pool" und eine Sicherungsregistrierungsstelle ausgewählt haben, können Sie das Kontrollkästchen der Option **Automatisches Failover und Failback für Sprachdienste** aktivieren. Danach können Sie numerische Eigenschaften für **Erkennungsintervall für Sprachdienstfehler (Sek.)** und **Failbackintervall für Sprache (Sek.)** definieren. Ausführliche Informationen finden Sie unter [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx).

  **Webdienste**

- Zum Konfigurieren von **Interne Webdienste** definieren Sie **Überwachungsports** für **HTTP** und **HTTPS**. Standardmäßig sind dies TCP-Port 80 bzw. TCP-Port 443. Sie können auch die Option **Veröffentlichte Ports** für **HTTP** und **HTTPS** konfigurieren. Standardmäßig sind dies TCP-Port 80 bzw. TCP-Port 443. Passen Sie die Portwerte basierend auf der Konfiguration der internen Webdienste und Verwendung des Lastenausgleichs (Hardwarelastenausgleich und DNS-Lastenausgleich) an, um die Überwachungsports und veröffentlichten Ports zu definieren.

    > [!IMPORTANT]
    > Interne Webdienste und die definierten Überwachungsports und veröffentlichten Ports gelten für interne Clients und Geräte. Für externe Clients und Geräte werden die Überwachungsports und veröffentlichten Ports der externen Webdienste in Verbindung mit dem definierten vollqualifizierten Domänennamen (FQDN) der externen Webdienste verwendet.

- Zum Konfigurieren von **Externe Webdienste** definieren Sie **Überwachungsports** für **HTTP** und **HTTPS**. Standardmäßig sind dies TCP-Port 80 bzw. TCP-Port 443. Sie können auch die Option **Veröffentlichte Ports** für **HTTP** und **HTTPS** konfigurieren. Standardmäßig sind dies TCP-Port 80 bzw. TCP-Port 443. Passen Sie die Portwerte basierend auf der Konfiguration der internen Webdienste und Verwendung des Lastenausgleichs (Hardwarelastenausgleich und DNS-Lastenausgleich) an, um die Überwachungsports und veröffentlichten Ports zu definieren.

    > [!IMPORTANT]
    > Externe Webdienste und die definierten Überwachungsports und veröffentlichten Ports gelten für externe Clients und Geräte. Für externe Clients und Geräte werden die Überwachungsports und veröffentlichten Ports der externen Webdienste (normalerweise vom Reverseproxy definiert) in Verbindung mit dem definierten vollqualifizierten Domänennamen (FQDN) der externen Webdienste verwendet. Die Beziehung des FQDN der externen Webdienste und von Einfache URLs definiert die URL-Adressen (Uniform Resource Locator), die von externen Clients zum Zugreifen auf die für externe Besucher und Geräte verfügbaren Dienste verwendet werden. Ausführliche Informationen zu einfachen URLs finden Sie unter [Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Vermittlungsserver**

- Wählen Sie **zum** Konfigurieren der Eigenschaften des Vermittlungsservers für einen ausgeführten Vermittlungsserver (d. h. einen auf dem Front-End-Server oder Front-End-Pool bereitgestellten Vermittlungsserver) die Option **"Collocated Mediation server enabled" aus.**

- Um die  Abhörports für einen verbundener Vermittlungsserver zu definieren, geben Sie den **TLS-** und den **TCP-Portwert** ein, den der verbundene Vermittlungsserver abhört. Standardmäßig ist TLS als TCP-Port 5067 definiert.

- Aktivieren Sie das Kontrollkästchen TCP-Port aktivieren, um einen Wert für den **Vermittlungsserver** zu definieren. Standardmäßig verwendet der Vermittlungsserver TLS (Transport Layer Security) über das TCP-Protokoll. TCP-Ports sind nur verfügbar, wenn die Option "TCP-Port aktivieren" aktiviert ist.

    > [!NOTE]
    > Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.

- Sie definieren Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

    Wenn einem Vermittlungsserver mehrere Gateways zugeordnet sind, können Sie das Standardgateway angeben, indem Sie das Gateway auswählen, das Als Standardeinstellung festgelegt werden soll, und auf **"Standard" klicken.** Falls Sie das aktuelle Standardgateway entfernen möchten, wählen Sie das Gateway aus und klicken auf **Festlegung als Standardeinstellung aufheben**.

> [!IMPORTANT]
> Wenn Sie in diesem Dialogfeld Änderungen an den Eigenschaften vornehmen, müssen Sie die Topologie veröffentlichen und den Skype for Business Server-Bereitstellungs-Assistenten auf allen betroffenen Servern ausführen. Nach der Veröffentlichung der neuen Topologie wird eine Liste der betroffenen Server, auf denen der Skype for Business Server-Bereitstellungs-Assistent ausgeführt werden muss, als Link auf dem Zusammenfassungsbildschirm für die erfolgreiche Topologieveröffentlichung bereitgestellt. Ausführliche Informationen zur Veröffentlichung der aktualisierten Topologie finden Sie unter [Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Weitere Informationen zum Skype for Business Server-Bereitstellungs-Assistenten finden Sie unter ["Lync Server-Verwaltungstools".](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx)

Klicken Sie auf **OK**, um die Änderungen des Topologiedokuments zu speichern und zu übernehmen.

Klicken **Sie auf "Abbrechen",** um die Änderungen zu verwerfen und die Eigenschaften für den Front-End-Server oder front-End-Pool zu schließen. 

Klicken Sie auf **Hilfe**, um dieses Hilfethema anzuzeigen.

## <a name="see-also"></a>Siehe auch

[Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
