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
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Sie bearbeiten die Einstellungen für die Edgeserver oder Edgepool, indem Sie die folgenden Eigenschaften konfigurieren:'
ms.openlocfilehash: ab558edd16370d46d452f4e3d146dbf2153f3d9e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216116"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung
 
Sie bearbeiten die Einstellungen für die Edgeserver oder Edgepool, indem Sie die folgenden Eigenschaften konfigurieren: 
  
 **Allgemein**
  
- **Interner FQDN des Pools**: der vollqualifizierte Domänenname des internen Pools ist die Identität der Edgeserver oder Edgepool, die im DNS-Eintrag (Domain Name System) (DNS)-Host (A oder AAAA für IPv6) definiert ist.
    
- Wählen Sie Partner **Verbund für diesen Edgepool aktivieren (Port 5061)** aus, wenn Sie die Edgeserver oder Edgepool für den Verbund mit anderen Session Initiation Protocol-Partnern aktivieren möchten.
    
    > [!IMPORTANT]
    > Sie können nur eine Edgeserver oder aktiv für den Verbund Edgepool definieren. Die im dazugehörigen Screenshot angezeigte Konfiguration gibt an, dass bereits ein anderes Edgeserver oder Edgepool für den Verbund konfiguriert ist. Der externe DNS-SRV-Eintrag für den Verbund (_sipfederationtls. _tcp. \<external domain name\> ) zeigt auf den Edgeserver oder Edgepool für den Verbund. 
  
- Der **interne Konfigurations Replikations Port (HTTPS)** ist standardmäßig am TCP-Port 4443 der Port, über den die lokale Kopie des zentralen Verwaltungsspeichers (lokal für die Edgeserver) repliziert wird. Die lokale Kopie des zentralen Verwaltungsspeichers befindet sich in der SQL Server auf jedem Computer in der **RTCLOCAL** -Datenbank. Die Replikation erfolgt unidirektional, initiiert vom zentralen Verwaltungsserver (oder dem Front-End-Server oder Front-End-Pool mit der zentralen Verwaltungsserverrolle) auf den Edgeserver und ist ein interner Schnittstellen Port.
    
  **Auswahl für nächsten Hop**
  
- Treffen Sie in der Liste **Nächster Hoppool** eine Auswahl. Sie definieren entweder einen Director, Directorpool, Front-End-Server oder Front-End-Pool, um diese Rolle zu übernehmen. Der Pool für den nächsten Hop ist der Server oder Serverpool, der eingehende SIP-Nachrichten vom Edgeserver oder Edgepool internen Schnittstelle akzeptiert und ausgehende SIP an die interne Edge-Schnittstelle sendet.
    
    > [!NOTE]
    > Der Director ist eine optionale Rolle, und wenn Sie Directors nicht bereitstellen möchten, übernehmen die Front-End-Server (einzelner Computer oder Pool) die Director-Rolle. 
  
  **Externe Einstellungen**
  
In diesem Abschnitt der Eigenschaften können Sie Eigenschaften für die externen Einstellungen des Edgeserver oder Edgepool bearbeiten. Die folgenden Eigenschaften stehen zur Bearbeitung zur Verfügung:
  
- Aktivieren Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** , wenn Sie jedem Edgeserver Dienst unterschiedliche IP-Adressen und vollqualifizierte Domänennamen zuweisen möchten.
    
    > [!NOTE]
    > Wenn Sie das Kontrollkästchen nicht aktivieren, müssen Sie für jeden Edgedienst separate Ports verwenden. Jeder Edgedienst gibt den für die Zugriffs-Edgedienst definierten FQDN frei und verwendet daher dieselbe IP-Adresse. Jeder Edgedienst muss entweder mit einer separaten IP-Adresse und demselben Port oder derselben IP-Adresse und separaten Portwerten eindeutig identifiziert werden. 
  
- Wählen Sie **A/V-Edgedienst ist NAT aktiviert** aus, wenn Sie die A/V-Edgedienst so konfigurieren möchten, dass eine private Adresse oder andere Adresse verwendet wird, die hinter einem NAT-Gerät (Network Address Translation, Netzwerkadressübersetzung) verborgen ist.
    
- Um die **Zugriffs-Edgedienst**zu bearbeiten, definieren Sie den **Pool-FQDN** für die Zugriffs-Edgedienst, wie in DNS durch Host definiert (A und AAAA, wenn IPv6 verwendet wird), Datensätze und einen Portwert.
    
- Um die **Webkonferenz-Edgedienst**zu bearbeiten, definieren Sie einen **Pool-FQDN** für die Webkonferenz-Edgedienst, wie in DNS durch Host definiert (a und AAAA, wenn IPv6 verwendet wird), Datensätze und einen Portwert
    
- Um die **A/V-Edgedienst**zu bearbeiten, definieren Sie einen **Pool-FQDN** für die A/V-Edgedienst, wie in DNS durch Host definiert (A und AAAA, wenn IPv6 verwendet wird), Datensätze und einen Portwert
    
    > [!IMPORTANT]
    > Wenn Sie das Kontrollkästchen **separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** aktiviert haben, steht nur der FQDN des Zugriffs-Edgedienst Pools zur Bearbeitung zur Verfügung. Weisen Sie für die drei Edgedienste jeweils unterschiedliche Ports zu.
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen, und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

