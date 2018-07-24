---
title: Überprüfen der Replikation der Schemapartition
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 'Um zu überprüfen, ob die schemaerweiterung erfolgreich in Ihrer Active Directory-Domänendienste-Gesamtstruktur repliziert wurden, führen Sie folgende Schritte aus:'
ms.openlocfilehash: bfcc5cba79f023c746aac3d5c312871003f333b2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020465"
---
# <a name="verify-replication-of-schema-partition"></a>Überprüfen der Replikation der Schemapartition
 
Um zu überprüfen, ob die schemaerweiterung erfolgreich in Ihrer Active Directory-Domänendienste-Gesamtstruktur repliziert wurden, führen Sie folgende Schritte aus:
  
1. Melden Sie sich an einem Domänencontroller (mit Ausnahme der Domänencontroller, der die Schemamasterrolle enthält) in Ihrer Active Directory-Domänendienste-Gesamtstruktur, in dem durch die schemaerweiterungen, als Mitglied der Gruppe Organisations-Admins angewendet wurden an.
    
2. Open ADSI-Editor: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **ADSI-Bearbeitung**.
    
    > [!TIP]
    > Alternativ klicken Sie auf **Start**und dann auf **Ausführen**, **adsiedit.msc** eingeben, starten Sie ADSI Edit.
  
3. Erweitern Sie in der Microsoft Management Console (MMC), wenn es nicht bereits aktiviert ist, klicken Sie auf ADSI-Bearbeitung.
    
4. Klicken Sie im Menü **Aktion** auf **Verbinden mit**.
    
5. Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus und klicken Sie dann auf **OK**.
    
6. Suchen Sie unter dem Schemacontainer nach CN=ms-RTC-SIP-SchemaVersion. Wenn dieses Objekt vorhanden ist, und der Wert des **RangeUpper** -Attributs 1150 und der Wert des Attributs **RangeLower** 3 ist, wurde klicken Sie dann das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder wenn die Werte der Attribute **RangeUpper** und **RangeLower** nicht als sind angegeben, klicken Sie dann das Schema nicht geändert wurde oder nicht repliziert wurde.
    
> [!NOTE]
> Wenn die Kontrollkästchen der Replikation des Schemas eine erfolgreiche Replikation noch nicht angezeigt wird, warten Sie etwa 15 Minuten und dann erneut. Active Directory-Replikation wird basierend auf einem Modell lose Konsistenz und einige Replikationslatenz auftreten kann, basierend auf einer Reihe von Faktoren in den Server- und Infrastruktur. 
  

