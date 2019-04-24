---
title: Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 'Bearbeiten Sie die Einstellungen für den Edge-Server oder Edge-Pool, indem Sie die folgenden Eigenschaften konfigurieren:'
ms.openlocfilehash: a4ad88aa6ff565ac7c1ebb5134d476d34625418f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203130"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Bearbeiten der Edgeeinstellungen für Lync Server 2010 – Erweiterung
 
Bearbeiten Sie die Einstellungen für den Edge-Server oder Edge-Pool, indem Sie die folgenden Eigenschaften konfigurieren: 
  
 **Allgemein**
  
- **Interner FQDN des Pools**: der vollqualifizierten Domänennamen des internen Pool ist die Identität des Edge-Server oder Edge-Pools, wie im Domain Name System (DNS) Host (A oder AAAA für IPv6) Datensatz definiert.
    
- Wählen Sie **aktivieren den Verbund für diesen edgepool (Port 5061)** aus, wenn Sie den Edgeserver oder edgepool für den Verbund mit anderen Session Initiation Protocol-Partnern aktivieren möchten.
    
    > [!IMPORTANT]
    > Sie können nur auf einem Edge-Server oder Edge-Pool aktiv für den Verbund definieren. Die Konfiguration der zugehörige Screenshot dargestellt gibt an, dass bereits einen anderen Edgeserver oder Edge-Pool für den Verbund konfiguriert ist. Der externe DNS-SRV-Eintrag für den Verbund (_sipfederationtls.\< externe Domänennamen\>) verweist auf den Edgeserver oder edgepool für den Verbund. 
  
- Die **Interne Konfiguration Replikation Port (HTTPS)**, die standardmäßig auf TCP-Port 4443, ist der Port, der lokalen Kopie (d. h., lokal auf den Edge-Servern) Kopie des zentralen Verwaltungsspeichers über repliziert wird. Die lokale Kopie des zentralen Verwaltungsspeichers ist in die **RTCLOCAL** -Datenbank in SQL Server auf jedem Computer. Die Replikation ist unidirektional, initiiert aus den zentralen Verwaltungsserver (oder die Front-End-Server oder Front-End-Pool, der die Rolle des zentralen Verwaltungsservers beinhaltet) mit den Edgeservern und ein Port für die interne Schnittstelle ist.
    
  **Auswahl für nächsten hop**
  
- Wählen Sie den **nächsten hoppool**, für die Liste aus. Sie definieren Sie entweder einen Director, Director-Pool Front-End-Server oder Front-End-Pool dieser Rolle übernehmen. Der nächste hoppool ist der Server oder Serverpool, die eingehende SIP-Nachrichten vom Edge-Server akzeptieren oder interne Schnittstelle des Edgeservers Pool und Senden ausgehender SIP an die interne Schnittstelle des Edgeservers.
    
    > [!NOTE]
    > Der Director ist eine optionale Rolle, und wenn Sie sich, keine Director-Server bereitstellen entscheiden, wird die Front-End-Server (einzelner Computer oder Pool) die Director-Rolle voraus. 
  
  **Einstellungen für externe**
  
In diesem Abschnitt der Eigenschaften können Sie Eigenschaften für die externen Einstellungen des Edge-Server oder Edge-Pools zu bearbeiten. Die folgenden Eigenschaften stehen zur Bearbeitung zur Verfügung:
  
- Wählen Sie aus der **Enable separaten FQDN und IP-Adressen für Webkonferenzen und A / V** das Kontrollkästchen, wenn Sie unterschiedliche IP-Adressen und vollqualifizierten Domänennamen zuweisen möchten den Namen für jeden Dienst Edge-Server.
    
    > [!NOTE]
    > Wenn Sie das Kontrollkästchen nicht aktivieren möchten, müssen Sie für jeden Dienst Edge eigenen Port verwenden. Jeder edgedienst nutzen den FQDN für Zugriffs-edgediensts definiert und wird daher dieselbe IP-Adresse verwenden. Jeder edgedienst muss eindeutig identifiziert werden, indem eine unterschiedliche IP-Adresse und denselben Port oder der dieselbe IP-Adresse und eindeutige Portwerte. 
  
- Wählen Sie **A / V-edgedienst ist für NAT aktiviert** Wenn Sie A konfigurieren möchten a / V-edgedienst verwenden eine private Adresse oder andere Adresse, die hinter einem Gerät Network Address Translation (NAT) ausgeblendet ist.
    
- Um den **Zugriffs-edgedienst**zu bearbeiten, definieren Sie den **Pool-FQDN** für Zugriffs-edgediensts gemäß Definition im DNS vom Host (A und AAAA Wenn IPv6 verwendet wird) Datensätze und einen Port-Wert
    
- Um den **Webkonferenz-edgedienst**zu bearbeiten, definieren Sie einen **Pool-FQDN** für den Webkonferenz-edgedienst gemäß Definition im DNS vom Host (A und AAAA Wenn IPv6 verwendet wird) Datensätze und einen Port-Wert
    
- So bearbeiten Sie die **A / V-edgedienst**, definieren Sie einen **Pool-FQDN** für den A / V-edgedienst gemäß Definition im DNS vom Host (A und AAAA Wenn IPv6 verwendet wird) Datensätze und einen Port-Wert
    
    > [!IMPORTANT]
    > Wenn Sie ausgewählt haben, haben die **Enable separaten FQDN und IP-Adressen für Webkonferenzen und A / V** das Kontrollkästchen nur der Zugriffs-edgedienst Pool-FQDN wird zur Bearbeitung verfügbar sein. Weisen Sie unterschiedliche Ports für jede der drei edgedienste.
  
  **OK**: Mit dieser Option werden die Änderungen am Dialogfeld akzeptiert und übernommen.
  
  **Abbrechen**: Mit dieser Option werden die Änderungen verworfen und das Dialogfeld wird geschlossen.
  
  **Hilfe**: Mit dieser Option zeigen Sie diese Hilfeseite an.
  

