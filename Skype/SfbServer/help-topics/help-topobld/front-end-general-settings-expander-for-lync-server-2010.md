---
title: Allgemeine Einstellungen für das Front-End für Lync Server 2010 – Erweiterung
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
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Sie können die Eigenschaften des Front-End-Servers oder des Front-End-Pools bearbeiten, indem Sie die folgenden Attribute bearbeiten oder konfigurieren. Die Konfigurationsseite ist in die folgenden Abschnitte unterteilt:'
ms.openlocfilehash: c417cd95d43354ad2466138ef6c9382c1a2cd00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819897"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Allgemeine Einstellungen für das Front-End für Lync Server 2010 – Erweiterung

Sie können die Eigenschaften des Front-End-Servers oder des Front-End-Pools bearbeiten, indem Sie die folgenden Attribute bearbeiten oder konfigurieren. Die Konfigurationsseite ist in die folgenden Abschnitte unterteilt:

 **Allgemein**

- **FQDN**: der vollqualifizierte Domänenname des Front-End-Servers oder des Front-End-Pools.

- Wählen Sie **alle konfigurierten IP-Adressen verwenden** aus, um alle Adressen zu verwenden, die auf dem Front-End-Server oder Front-End-Pool konfiguriert sind.

    > [!IMPORTANT]
    > Wählen Sie diese Option nicht aus, wenn Sie den Vermittlungsserver auf dem Front-End-Server oder Front-End-Pool collocate. Vermittlungsserver und Front-End-Server benötigen dedizierte IP-Adressen für die Kommunikation.

- Wählen Sie **Dienst Verwendung auf ausgewählte IP-Adressen einschränken** aus, und geben Sie die IP-Adresse für die **primäre IP-Adresse** für den Front-End-Server oder die Kommunikation des Front-End-Pools mit der restlichen Bereitstellung ein. Geben Sie die IP-Adresse, die dem Vermittlungs Server zugeordnet ist, in **PSTN-IP-Adresse** ein.

    **Features und Funktionen**

- **Konferenz**: Aktivieren Sie das Kontrollkästchen, wenn Konferenzfeatures in Ihrer Bereitstellung angezeigt werden sollen. Konferenz umfasst Audio, Video, Anwendungsfreigabe, Desktopfreigabe und Webkonferenzen. Sie müssen einen Office Web Apps-Server für Webkonferenzen erstellen und zuordnen (wird später auf dieser Eigenschaftenseite definiert).

- Wenn Sie Konferenzen ausgewählt haben, können **Einwahlkonferenzen (PSTN)** ausgewählt werden. Aktivieren Sie das Kontrollkästchen, um Features für Einwahlkonferenzen zu aktivieren.

- Aktivieren Sie das Kontrollkästchen **Enterprise-VoIP** , wenn Sie Features bereitstellen möchten, um die Verwendung von lync Server 2013 als Telefon-VoIP-System mithilfe von VoIP-Technologien (Voice over IP) zu ermöglichen, einschließlich der Option zum Bereitstellen von Telefonen, SIP-Stämmen oder öffentlichen Telefonnetzen mithilfe von Vermittlungs Server, PSTN-Gateways und IP-PBX, basierend auf dem Einzelheiten zu Enterprise-VoIP finden Sie unter [Enterprise](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) -VoIP und [Plan für Enterprise-VoIP in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

    **Zuordnungen**

- **SQL Server Store**: der FQDN des SQL Server (und optional eine benannte Instanz), der dem Front-End-Server oder Front-End-Pool zugeordnet ist. Sie wählen den SQL Server-Speicher aus der Liste aus, oder Sie erstellen einen neuen SQL Server-Speicher, indem Sie auf **neu** klicken.

- **Dateispeicher**: Sie wählen den FQDN des Servers und die Freigabe (im Format `\\<FQDN of server>\<share name>`) aus, die als Dateispeicher Speicherort für die freigegebenen Dateien fungiert, die von lync Server 2013 erstellt und für die Replikation, Konferenzverzeichnisse und andere Zwecke verwendet werden. Sie wählen den Dateispeicher in der Liste aus, oder Sie erstellen einen neuen Dateispeicher, indem Sie auf **neu**klicken.

- Aktivieren Sie das Kontrollkästchen **Archivierungsserver zuordnen** , um einen Archivierungsserver für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nachdem Sie das Kontrollkästchen aktiviert haben, wählen Sie einen vorhandenen Archivierungsserver aus der Liste aus, oder klicken Sie auf **neu** , um die Definitionen für einen neuen Archivierungsserver zu erstellen.

- Aktivieren Sie das Kontrollkästchen **Überwachungsserver zuordnen** , um einen Überwachungsserver für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nachdem Sie das Kontrollkästchen aktiviert haben, wählen Sie einen vorhandenen Überwachungsserver aus der Liste aus, oder klicken Sie auf **neu** , um die Definitionen für einen neuen Überwachungsserver zu erstellen.

- Aktivieren Sie das Kontrollkästchen **Edge-Pool zuordnen (für Medienkomponenten** , um einen Edgeserver für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nachdem Sie das Kontrollkästchen aktiviert haben, wählen Sie einen vorhandenen Edgeserver oder Pool in der Liste aus, oder klicken Sie auf **neu** , um die Definitionen für einen neuen Edgeserver oder Pool zu erstellen.

  **Flexibilität**

- Aktivieren Sie das Kontrollkästchen **zugeordnete sicherungsregistrierungspool** , um aus der Liste einen Front-End-Server oder einen Front-End-Pool zu wählen, der als Sicherungs Registrierungsstelle (also der Front-End-Server oder Front-End-Pool als sekundäre Registrierungsstelle bezeichnet wird, falls der primäre Fehler auftritt)

- Wenn Sie den entsprechenden sicherungsregistrierungspool ausgewählt und eine Sicherungs Registrierungsstelle ausgewählt haben, können Sie das Kontrollkästchen für **Automatisches Failover und Failback für VoIP**aktivieren. Sie können jetzt numerische Eigenschaften für die **interne (SEK)-Spracherkennung** und das **Failback-Intervall für Sprachanrufe (sec)** definieren. Ausführliche Informationen finden Sie unter [Planen der Enterprise-VoIP-Resilienz](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)

  **Web Services**

- Zum Konfigurieren **interner Webdienste**definieren Sie **Abhör-Ports** für **http** und **https**. Standardmäßig handelt es sich hierbei um TCP-Port 80 und TCP-Port 443. Darüber hinaus konfigurieren Sie die **veröffentlichten Ports** für **http** und **https**. Standardmäßig handelt es sich hierbei um TCP-Port 80 und TCP-Port 443. Passen Sie auf der Grundlage ihrer internen Webdienstkonfiguration und der Verwendung von Lastenausgleichsgeräten (Hardwarelastenausgleichs und DNS-Lastenausgleich) die Portwerte an, um die anhörenden und veröffentlichten Ports zu definieren.

    > [!IMPORTANT]
    > Interne Webdienste und die definierten Überwachungs-und Veröffentlichungs-Ports sind für interne Clients und Geräte bestimmt. Externe Clients und Geräte verwenden die externen Webdienste Überwachung und veröffentlichte Ports sowie den definierten externen Webdienste-vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN).

- Zum Konfigurieren **externer Webdienste**definieren Sie **Abhör-Ports** für **http** und **https**. Standardmäßig handelt es sich hierbei um TCP-Port 80 und TCP-Port 443. Darüber hinaus konfigurieren Sie die **veröffentlichten Ports** für **http** und **https**. Standardmäßig handelt es sich hierbei um TCP-Port 80 und TCP-Port 443. Passen Sie auf der Grundlage ihrer internen Webdienstkonfiguration und der Verwendung von Lastenausgleichsgeräten (Hardwarelastenausgleichs und DNS-Lastenausgleich) die Portwerte an, um die anhörenden und veröffentlichten Ports zu definieren.

    > [!IMPORTANT]
    > Externe Webdienste und die definierten Überwachungs-und Veröffentlichungs-Ports gelten für externe Clients und Geräte. Externe Clients und Geräte verwenden die überwachten und veröffentlichten Ports für externe Webdienste, die in der Regel von Ihrem Reverseproxy zusammen mit dem definierten externen Webdienste-vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) definiert werden. Die Beziehung zwischen dem FQDN externer Webdienste und den einfachen URLs definiert die URL-Adressen (Uniform Resource Locator), die von externen Clients für den Zugriff auf Dienste verwendet werden, die für externe Benutzer und Geräte verfügbar sind. Weitere Informationen zu einfachen URLs finden Sie unter [Planen einfacher URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).

  **Vermittlungsserver**

- Wenn Sie die **Vermittlungsserver** Eigenschaften für einen eingerichteten Vermittlungsserver (also einen auf dem Front-End-Server oder Front-End-Pool bereitgestellten Vermittlungsserver) konfigurieren möchten, wählen Sie zusammengestellt **Mediation Server aktiviert**aus.

- Wenn Sie die **Überwachungsanschlüsse** für einen bereitgestellten Vermittlungsserver definieren möchten, geben Sie den Wert für **TLS** und **TCP** -Port ein, der vom beiliegenden Vermittlungsserver überwacht wird. Standardmäßig ist TLS als TCP-Port 5067 definiert.

- Wenn Sie einen TCP-Portwert für den Vermittlungs Server definieren möchten, aktivieren Sie das Kontrollkästchen **TCP-Port aktivieren** . Standardmäßig verwendet der Vermittlungs Server das TLS (Transport Layer Security) over TCP-Protokoll. TCP-Ports sind nur verfügbar, wenn die Option TCP-Port aktivieren aktiviert ist.

    > [!NOTE]
    > Hierbei handelt es sich um eine optionale Einstellung, und Sie sollten sich auf die Anforderungen Ihres Gateways oder PSTNs beziehen, um festzustellen, ob dies erforderlich ist. Standardmäßig ist der TCP-Port-Wert 5068.

- Sie definieren Trunks, die dem zusammengefassten Vermittlungs Server zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

    Wenn einem Vermittlungs Server mehr als ein Gateway zugeordnet ist, können Sie das Standardgateway angeben, indem Sie das Gateway auswählen, das Sie als Standard festlegen möchten, und dann auf **als Standard festlegen klicken.** Wenn Sie sich entscheiden, das aktuelle Standardgateway zu entfernen, wählen Sie das Gateway aus, und klicken Sie auf **Standard aufheben**.

> [!IMPORTANT]
> Wenn Sie Änderungen an den Eigenschaften in diesem Dialogfeld vornehmen, müssen Sie die Topologie veröffentlichen und den Bereitstellungs-Assistenten für Skype for Business Server auf allen betroffenen Servern ausführen. Nach der Veröffentlichung der neuen Topologie wird eine Liste der betroffenen Server, auf denen der Skype for Business Server-Bereitstellungs-Assistent ausgeführt werden muss, als Link auf dem Zusammenfassungsbildschirm der erfolgreichen Topologie-Veröffentlichung bereitgestellt. Details zum Veröffentlichen der aktualisierten Topologie finden Sie unter [Veröffentlichen der Topologie](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Details zum Skype for Business Server-Bereitstellungs-Assistenten finden Sie unter [lync Server-Verwaltungs Tools](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).

Klicken Sie auf **OK** , um Ihre Änderungen im Topologie-Dokument zu speichern und zu übernehmen.

Klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen und die **Bearbeitungseigenschaften** für den Front-End-Server oder den Front-End-Pool zu schließen.

Klicken Sie auf **Hilfe** , um dieses Hilfethema zu lesen.

## <a name="see-also"></a>Siehe auch

[Definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
