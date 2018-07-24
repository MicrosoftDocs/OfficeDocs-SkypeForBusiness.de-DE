---
title: Hinzufügen von Datenbanken zu einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Zusammenfassung: Erfahren Sie, wie eine vorhandene AlwaysOn Availability Group in Skype Weitere Skype für Business Server-Datenbanken für Business Server hinzuzufügen.'
ms.openlocfilehash: f055466788494f10575b7bd3710705a138c456b2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976324"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a>Hinzufügen von Datenbanken zu einer AlwaysOn-Verfügbarkeitsgruppe in Skype für Business Server
 
**Zusammenfassung:** Erfahren Sie, wie eine vorhandene AlwaysOn Availability Group in Skype Weitere Skype für Business Server-Datenbanken für Business Server hinzuzufügen.
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>Hinzufügen von Datenbanken zu einer AlwaysOn-Verfügbarkeitsgruppe

1. Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AlwaysOn Availability Group. Failover es auf das primäre Replikat.
    
2. Legen Sie die SQL Server-FQDN der AlwaysOn Availability Group im Topologie-Generator auf den vollqualifizierten Domänennamen des primären Knotens der Gruppe.
    
  - Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.
    
  - Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**. Mit der rechten Maustaste in des SQL-Speichers der neuen AlwaysOn Availability Group, und klicken Sie auf **Eigenschaften bearbeiten**.
    
  - Geben Sie am unteren Rand der Seite in das Feld **SQL Server-FQDN** in den FQDN des primären Knoten die AlwaysOn Availability Group.
    
3. Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.
    
4. Verwenden Sie SQL Server Management Studio die AlwaysOn Availability Group die neue Datenbank hinzu.
    

