---
title: Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Sie bearbeiten die Einstellungen für den Edgeserver oder Edgepool, indem Sie die folgenden Eigenschaften konfigurieren:'
---

# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung
 
Sie bearbeiten die Einstellungen für den Edgeserver oder Edgepool, indem Sie die folgenden Eigenschaften konfigurieren: 
  
 **Allgemein**
  
- **Interner Pool-FQDN**: Der vollqualifizierte Domänenname des internen Pools ist die Identität des Edgeservers oder Edgepools gemäß definition im DNS-Hosteintrag (A oder AAAA für IPv6).
    
- Wählen Sie **"Partnerverbund für diesen Edgepool aktivieren" (Port 5061) aus** , wenn Sie den Edgeserver oder Edgepool für den Partnerverbund mit anderen Sitzungsinitiierungsprotokollpartnern aktivieren möchten.
    
    > [!IMPORTANT]
    > Sie können nur einen Edgeserver oder Edgepool aktiv für einen Partnerverbund definieren. Die im zugehörigen Screenshot gezeigte Konfiguration weist darauf hin, dass ein anderer Edgeserver oder Edgepool bereits für den Partnerverbund konfiguriert ist. Der externe DNS-SRV-Eintrag für den Partnerverbund (_sipfederationtls._tcp.\<external domain name\>) verweist auf den Edgeserver oder Edgepool für den Partnerverbund. 
  
- Der **interne Configuration Replication Port (HTTPS)** ist standardmäßig bei TCP-Port 4443 der Port, über den die lokale Kopie (d. h. lokal auf den Edgeservern) des zentralen Verwaltungsspeichers repliziert wird. Die lokale Kopie des zentralen Verwaltungsspeichers befindet sich in der **RTCLOCAL-Datenbank** im SQL Server auf jedem Computer. Die Replikation erfolgt unidirektional, wird vom zentralen Verwaltungsserver (oder dem Front-End-Server oder Front-End-Pool mit der Rolle des zentralen Verwaltungsservers) zu den Edgeservern initiiert und ist ein interner Schnittstellenport.
    
  **Auswahl für nächsten Hop**
  
- Treffen Sie in der Liste **Nächster Hoppool** eine Auswahl. Sie definieren entweder einen Director, Director-Pool, Front-End-Server oder Front-End-Pool, um diese Rolle zu übernehmen. Der nächste Hoppool ist der Server oder Serverpool, der eingehende SIP-Nachrichten von der internen Schnittstelle des Edgeservers oder Edgepools akzeptiert und ausgehende SIP-Nachrichten an die interne Edgeschnittstelle sendet.
    
    > [!NOTE]
    > Der Director ist eine optionale Rolle, und wenn Sie sich entscheiden, Directors nicht bereitzustellen, übernehmen die Front-End-Server (einzelner Computer oder Pool) die Directorrolle. 
  
  **Externe Einstellungen**
  
In diesem Abschnitt der Eigenschaften können Sie Eigenschaften für die externen Einstellungen des Edgeservers oder Edgepools bearbeiten. Die folgenden Eigenschaften stehen zur Bearbeitung zur Verfügung:
  
- Aktivieren Sie das Kontrollkästchen **separate FQDN und IP-Adresse für Webkonferenzen und A/V** aktivieren, wenn Sie jedem Edgeserverdienst unterschiedliche IP-Adressen und vollqualifizierte Domänennamen zuweisen möchten.
    
    > [!NOTE]
    > Wenn Sie das Kontrollkästchen nicht aktivieren, müssen Sie für jeden Edgedienst separate Ports verwenden. Jeder Edgedienst verwendet den FQDN, der für den Zugriffs-Edgedienst definiert ist, und verwendet daher dieselbe IP-Adresse. Jeder Edgedienst muss entweder mit einer separaten IP-Adresse und demselben Port oder derselben IP-Adresse und separaten Portwerten eindeutig identifiziert werden. 
  
- Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.
    
- Zum Bearbeiten des **Zugriffs-Edgediensts** definieren Sie den **Pool-FQDN** für den Zugriffs-Edgedienst gemäß der Definition in DNS nach Hosteinträgen (A und AAAA, wenn IPv6 verwendet wird) und einem Portwert.
    
- Zum Bearbeiten des **Webkonferenz-Edgediensts** definieren Sie einen **Pool-FQDN** für den Webkonferenz-Edgedienst gemäß der Definition in DNS nach Hosteinträgen (A und AAAA, wenn IPv6 verwendet wird) und einem Portwert.
    
- Zum Bearbeiten des **A/V-Edgediensts** definieren Sie einen **Pool-FQDN** für den A/V-Edgedienst gemäß der Definition in DNS nach Hosteinträgen (A und AAAA, wenn IPv6 verwendet wird) und einem Portwert.
    
    > [!IMPORTANT]
    > Wenn Sie das Kontrollkästchen **separate FQDN und IP-Adresse für Webkonferenzen und A/V** aktiviert haben, steht nur der FQDN des Zugriffs-Edgedienstpools zur Bearbeitung zur Verfügung. Weisen Sie für die drei Edgedienste jeweils unterschiedliche Ports zu.
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

