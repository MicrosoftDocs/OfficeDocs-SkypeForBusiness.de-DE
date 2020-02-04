---
title: Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Sie bearbeiten die Einstellungen für den Edge-Server oder den Edge-Pool, indem Sie die folgenden Eigenschaften konfigurieren:'
ms.openlocfilehash: 78edbc8093b54474ac9f0429b5232851a5a16663
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697380"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung
 
Sie bearbeiten die Einstellungen für den Edge-Server oder den Edge-Pool, indem Sie die folgenden Eigenschaften konfigurieren: 
  
 **Allgemein**
  
- **Interner Pool-FQDN**: der vollqualifizierte Domänenname des internen Pools ist die Identität des Edge-Servers oder des Edge-Pools, wie er im DNS-Host (Domain Name System)-Eintrag (A oder AAAA für IPv6) definiert ist.
    
- Wählen Sie **Föderation für diesen Edge-Pool aktivieren (Port 5061)** aus, wenn Sie den Edgeserver oder den Edge-Pool für den Verbund mit anderen Sitzungs Initiierungs Protokoll Partnern aktivieren möchten.
    
    > [!IMPORTANT]
    > Sie können nur einen Edge-Server oder einen Edge-Pool für den Verbund aktiv definieren. Die in dem zugehörigen Screenshot angezeigte Konfiguration zeigt an, dass ein anderer Edgeserver oder Edge-Pool bereits für den Verbund konfiguriert ist. Der externe DNS-SRV-Eintrag für Federation (_sipfederationtls.\< _tcp. externer Domänenname\>) zeigt auf den Edgeserver oder den Edge-Pool für Federation. 
  
- Der **interne Konfigurations Replikations Port (HTTPS)** ist standardmäßig am TCP-Port 4443 der Port, auf dem die lokale (lokal für die Edgeserver) Kopie des zentralen Verwaltungsspeichers repliziert wurde. Die lokale Kopie des zentralen Verwaltungsspeichers befindet sich in der **RTCLOCAL** -Datenbank auf jedem Computer in SQL Server. Die Replikation erfolgt unidirektional, initiiert vom zentralen Verwaltungsserver (oder dem Front-End-Server oder Front-End-Pool, in dem sich die zentrale Verwaltungsserverrolle befindet) an die Edgeserver und ist ein interner Schnittstellenanschluss.
    
  **Nächster Hop-Auswahl**
  
- Wählen Sie für die Liste Ihren **nächsten Hop-Pool**aus. Sie definieren entweder einen Director-, Director-Pool, einen Front-End-Server oder einen Front-End-Pool, um diese Rolle zu übernehmen. Der Pool für den nächsten Hop ist der Server-oder Serverpool, der eingehende SIP-Nachrichten vom Edgeserver oder der internen Schnittstelle des Edge-Pools akzeptiert und ausgehende SIP an die interne Edge-Schnittstelle sendet.
    
    > [!NOTE]
    > Der Director ist eine optionale Rolle, und wenn Sie sich entschließen, Directors bereitzustellen, übernimmt der Front-End-Server (einzelner Computer oder Pool) die Director-Rolle. 
  
  **Externe Einstellungen**
  
In diesem Abschnitt der Eigenschaften können Sie Eigenschaften für die externen Einstellungen des Edge-Servers oder des Edge-Pools bearbeiten. Die folgenden Eigenschaften stehen zur Bearbeitung zur Verfügung:
  
- Aktivieren Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** , wenn Sie jedem Edge-Server-Dienst unterschiedliche IP-Adressen und vollständig qualifizierte Domänennamen zuweisen möchten.
    
    > [!NOTE]
    > Wenn Sie das Kontrollkästchen nicht aktivieren, müssen Sie für jeden Edgedienst separate Ports verwenden. Jeder Edgedienst gibt den für den Access Edge-Dienst definierten FQDN frei und verwendet daher die gleiche IP-Adresse. Jeder Edgedienst muss entweder durch eine eindeutige IP-Adresse und denselben Port oder die gleiche IP-Adresse und eindeutige Portwerte eindeutig identifiziert werden. 
  
- Wählen Sie **a/v-Edgedienst ist NAT aktiviert** aus, wenn Sie den a/v-Edgedienst so konfigurieren möchten, dass er eine private Adresse oder eine andere Adresse verwendet, die hinter einem NAT-Gerät (Network Address Translation) verborgen bleibt.
    
- Um den **Access-Edgedienst**zu bearbeiten, definieren Sie den **Pool-FQDN** für den Access-Edgedienst entsprechend der Definition in DNS nach Host (A und AAAA, wenn IPv6 verwendet wird) und einem Portwert
    
- Zum Bearbeiten des **Webkonferenz-Edgedienst**definieren Sie einen **Pool-FQDN** für den Webkonferenz-Edgedienst, wie er in DNS nach Host (a und AAAA, wenn IPv6 verwendet wird), Datensätzen und einem Portwert definiert.
    
- Um den **a/v-Edgedienst**zu bearbeiten, definieren Sie einen **Pool-FQDN** für den a/v-Edgedienst, wie er in DNS von Host (A und AAAA, wenn IPv6 verwendet wird), Datensätzen und einem Portwert definiert.
    
    > [!IMPORTANT]
    > Wenn Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** aktiviert haben, steht nur der FQDN des Access-Edge-Service-Pools für die Bearbeitung zur Verfügung. Weisen Sie für jeden der drei Edge-Dienste verschiedene Ports zu.
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

