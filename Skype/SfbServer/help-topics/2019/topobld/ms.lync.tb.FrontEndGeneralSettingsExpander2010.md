---
title: Allgemeine Front-End für Lync Server 2010-Einstellungen – Erweiterung
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 'Sie bearbeiten die Eigenschaften des Front-End-Server oder Front-End-Pools, bearbeiten oder konfigurieren die folgenden Attribute. Die Konfigurationsseite ist in die folgenden Abschnitte unterteilt:'
ms.openlocfilehash: 9b72d78b0c6e4c1278f23d794ca713e3fef772cf
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976717"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Allgemeine Front-End für Lync Server 2010-Einstellungen – Erweiterung
 
Sie bearbeiten die Eigenschaften des Front-End-Server oder Front-End-Pools, bearbeiten oder konfigurieren die folgenden Attribute. Die Konfigurationsseite ist in die folgenden Abschnitte unterteilt:
  
 **Allgemein**
  
- **FQDN**: den vollqualifizierten Domänennamen des Front-End-Server oder Front-End-Pools.
    
- Wählen Sie **Alle konfigurierte IP-Adressen verwenden** , um Stellen verwenden aller Adressen auf Front-End-Server oder Front-End-Pool konfiguriert ist.
    
    > [!IMPORTANT]
    > Sie sollten diese Option nicht auswählen, wenn Sie den Vermittlungsserver auf dem Front-End-Server oder Front-End-Pool verbinden. Vermittlungsserver und Front-End-Server benötigen dedizierte IP-Adressen auf dem die Kommunikation stattfinden. 
  
- Wählen Sie **Verwendung von Grenzwert ausgewählten IP-Adressen aus** , und geben Sie die IP-Adresse für die **primäre IP-Adresse** für die Front-End-Server oder Front-End-Pool-Kommunikation mit dem Rest der Bereitstellung. Geben Sie in **PSTN-IP-Adresse** die IP-Adresse, die der Vermittlungsserver zugeordnet ist.
    
    **Features und Funktionen**
    
- **Konferenzen**: Aktivieren Sie das Kontrollkästchen, wenn Sie Live Meeting-Features in Ihrer Bereitstellung verwenden möchten. Konferenzfunktionen beinhalten Audio, Video, Anwendungsfreigabe, Desktopfreigabe und Webkonferenzen. Sie müssen erstellen, und ordnen Sie einen Office Web Apps Server für Webkonferenzen (weiter unten in diesem Eigenschaftenseite definiert).
    
- Wenn Sie Live Meeting ausgewählt haben, können **einwahlkonferenzen (PSTN)** ausgewählt werden. Aktivieren Sie das Kontrollkästchen, um einwahlkonferenzen Features zu aktivieren.
    
- Aktivieren Sie das Kontrollkästchen **Enterprise-VoIP** , wenn Sie beabsichtigen, Funktionen, die in Lync Server 2013 als Ihr Telefon VoIP-System über Voice over IP (VoIP) Technologien, einschließlich der Option über die Bereitstellung von Hörer Telefone fungieren aktivieren, SIP-Trunks oder öffentlichen bereitstellen Telefonnetz Netzwerkkonnektivität Vermittlungsserver, PSTN-Gateways und IP-Nebenstellenanlage mit basierend zusammen oder einzeln auf den Entwurf und die Anforderungen an. Informationen über Enterprise-VoIP finden Sie unter [Enterprise-VoIP](http://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) und [Enterprise-VoIP in Skype für Business Server planen](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)
    
    **Zuordnungen**
    
- **SQL Server-Speicher**: der FQDN der SQL Server (und optional eine benannte Instanz) mit dem Front-End-Server oder Front-End-Pool verknüpft ist. Wählen Sie den SQL Server-Speicher aus der Liste aus, oder Sie einen neuen SQL Server-Speicher erstellen, indem Sie auf **neu**
    
- **Speichern der Datei**: Wählen Sie den FQDN des Servers und die Freigabe (im Format `\\<FQDN of server>\<share name>`) fungiert, die als den Dateispeicherort für die freigegebenen Dateien, die Lync Server 2013 erstellt und für die Replikation, konferenzverzeichnisse und andere Zwecke verwendet. Wählen Sie den Dateispeicher aus der Liste aus, oder erstellen Sie einen neuen Dateispeicher, indem Sie auf **neu**.
    
- Wählen Sie das Kontrollkästchen **Archivierungsserver zuordnen** , um einen Archivierungsserver für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nach dem Aktivieren des Kontrollkästchens, wählen Sie einen vorhandenen Archivierungsserver aus der Liste aus oder klicken Sie auf **neu** , um die Definitionen für den neuen Archivierungsserver erstellen.
    
- Wählen Sie das Kontrollkästchen **Monitoring Server zuordnen** , um einen Monitoring Server für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nach dem Aktivieren des Kontrollkästchens, wählen Sie eine vorhandene Monitoring Server aus der Liste aus oder klicken Sie auf **neu** , um die Definitionen für einen neuen Monitoring Server zu erstellen.
    
- Wählen Sie aus der **Edgepool zuordnen (für Medienkomponenten** Kontrollkästchen, um einen Edge-Server für diesen Front-End-Server oder Front-End-Pool zu aktivieren. Nach dem Aktivieren des Kontrollkästchens, wählen Sie eine vorhandene Edge-Server oder Pool aus der Liste aus oder klicken Sie auf **neu** , um die Definitionen für einen neuen Edge-Server oder Pool zu erstellen.
    
 **Resiliency**
  
- Wählen Sie das Kontrollkästchen **zugeordneter Sicherungsregistrierungsstellen-Pool** einen Front-End-Server oder Front-End-Pool aus der Liste auswählen, die Sicherungsregistrierung werden (d. h., die Front-End-Server oder Front-End-Pool, die als einer sekundären Registrierung den Fall, dass die primäre ein Fehler auftritt)
    
- Wenn Sie zugeordneter Sicherungsregistrierungsstellen-Pool ausgewählt und eine sicherungsregistrierung gewählt haben, können Sie das Kontrollkästchen für **Automatisches Failover und Failback für VoIP**aktivieren. Sie können jetzt numerische Eigenschaften für **VoIP-Failover-Erkennung interne (s)** und **VoIP Failback Intervall (s)** definieren. Weitere Informationen hierzu finden Sie unter [Planning for Enterprise Voice Resiliency](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
    
 **Webdienste**
  
- Um **interne Webdienste**konfigurieren, definieren Sie die **Überwachungsports** für **HTTP** und **HTTPS**. Standardmäßig sind diese TCP-Port 80 und TCP-Port 443. Sie können auch die **veröffentlichten Ports** für **HTTP** und **HTTPS**konfigurieren. Standardmäßig sind diese TCP-Port 80 und TCP-Port 443. Auf Grundlage der interne Web Services-Konfiguration und der Lastenausgleich (Hardwaregeräte zum Lastenausgleich und DNS-Lastenausgleich) verwenden, passen Sie die Portwerte so definieren Sie die überwachungs- und veröffentlichten Ports.
    
    > [!IMPORTANT]
    > Interne Webdienste und die definierten überwacht und veröffentlichten Ports sind für interne Clients und Geräten. Externe Clients und Geräten verwenden Sie die externen Webdienste überwacht und veröffentlichte Ports, zusammen mit den definierten externe Web Services vollqualifizierten Domänennamen (FQDN). 
  
- Zum Konfigurieren von **externen Webdiensten**, definieren Sie die **Überwachungsports** für **HTTP** und **HTTPS**. Standardmäßig sind diese TCP-Port 80 und TCP-Port 443. Sie können auch die **veröffentlichten Ports** für **HTTP** und **HTTPS**konfigurieren. Standardmäßig sind diese TCP-Port 80 und TCP-Port 443. Auf Grundlage der interne Web Services-Konfiguration und der Lastenausgleich (Hardwaregeräte zum Lastenausgleich und DNS-Lastenausgleich) verwenden, passen Sie die Portwerte so definieren Sie die überwachungs- und veröffentlichten Ports.
    
    > [!IMPORTANT]
    > Externe Webdienste und die definierten überwacht und veröffentlichten Ports sind für externe Clients und Geräten. Externe Clients und Geräten verwenden Sie die externen Webdienste überwacht und veröffentlichte Ports, die in der Regel durch Ihren Reverseproxy aufrufen zusammen mit den definierten externe Web Services vollqualifizierten Domänennamen (FQDN) definiert. Die Beziehung zwischen den externen FQDN der Webdienste und die einfachen URLs definieren die uniform Resource Locator (URL)-Adressen, die externe Clients verwendet werden, um die verfügbaren Dienste für externe Benutzer und Geräte zugreifen. Weitere Informationen zu einfachen URLs finden Sie unter [Planung für einfache URLs](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx). 
  
 **Vermittlungsserver**
  
- Wählen Sie zum Konfigurieren der Eigenschaften der **Vermittlungsserver** für einen verbundenen Vermittlungsserver (d. h., einen Vermittlungsserver auf dem Front-End-Server oder Front-End-Pool bereitgestellt wird) **verbundener Vermittlungsserver aktiviert**.
    
- Um die **Überwachungsports** für einen verbundenen Vermittlungsserver zu definieren, geben Sie den Wert **TLS** und **TCP-** Port, dem die verbundenen Vermittlungsserver abgehört wird. Standardmäßig ist TLS als TCP-Port 5067 definiert.
    
- Um einen Wert für TCP-Port für den Vermittlungsserver zu definieren, aktivieren Sie das Kontrollkästchen **Aktivieren TCP-Port** . Standardmäßig wird der Vermittlungsserver die Transport Layer Security (TLS) über TCP-Protokoll verwendet. TCP-Ports sind verfügbar, nur, wenn die Auswahl des TCP-Port aktivieren aktiviert ist.
    
    > [!NOTE]
    > Dies ist eine optionale Einstellung, und verweisen Sie auf die Anforderungen der PSTN-Gateway oder zu ermitteln, ob dies notwendig ist. Standardmäßig ist der Wert des TCP-Ports 5068. 
  
- Sie definieren Trunks, die verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.
    
    Wenn Sie mehr als ein Gateway einen Vermittlungsserver zugeordnet haben, können Sie das Standardgateway angeben, wählen das Gateway, das Sie als Standardansicht festlegen möchten, und auf **Als Standard**. Wenn Sie auswählen, um das Standard-Gateway zu entfernen, wählen Sie das Gateway, und klicken Sie auf **Standard Unmake**.
    
> [!IMPORTANT]
> Wenn Sie die Eigenschaften in diesem Dialogfeld ändern, müssen die Topologie zu veröffentlichen und die Skype für Business Server-Bereitstellungs-Assistenten auf allen betroffenen Servern ausführen. Nach der Veröffentlichung der neuen Topologie wird eine Liste der betroffenen Server, auf dem die Skype für Business Server-Bereitstellungs-Assistenten ausgeführt werden muss, als einen Link auf die Veröffentlichung erfolgreich Topologie-Zusammenfassung für Sie bereitgestellt. Ausführliche Informationen zum Veröffentlichen der aktualisierten Topologie finden Sie unter [Publish the Topology](http://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx). Ausführliche Informationen zum die Skype für Business Server-Bereitstellungs-Assistenten finden Sie unter [Lync Server Administrative Tools](http://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx). 
  
Klicken Sie auf **OK** , um zu speichern und die Änderungen in das topologiedokument zu übernehmen.
  
Klicken Sie auf **Abbrechen** , um die Änderungen zu verwerfen und schließen Sie die **Eigenschaften bearbeiten** für den Front-End-Server oder Front-End-Pool.
  
Klicken Sie auf **Hilfe** , um dieses Hilfethema anzuzeigen.
  
## <a name="see-also"></a>Siehe auch

[Definieren Sie und konfigurieren Sie eines Front-End-Pool oder Standard Edition-Server](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)