---
title: Überprüfen der Replikation der Schemapartition
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
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Gehen Sie wie folgt vor, um zu überprüfen, ob die Schemaerweiterung erfolgreich in Ihrer Active Directory-Domänendienst Struktur repliziert wurde:'
ms.openlocfilehash: f2e8c181f01e841ebc6b251d8215a8d448db0b04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823269"
---
# <a name="verify-replication-of-schema-partition"></a>Überprüfen der Replikation der Schemapartition
 
Gehen Sie wie folgt vor, um zu überprüfen, ob die Schemaerweiterung erfolgreich in Ihrer Active Directory-Domänendienst Struktur repliziert wurde:
  
1. Melden Sie sich bei einem Domänencontroller (mit Ausnahme des Domänencontrollers, der die Schemamasterrolle innehat) in Ihrer Active Directory-Domänendienste-Gesamtstruktur an, in der die Schemaerweiterungen als Mitglied der Gruppe "Organisations-Admins" angewendet wurden.
    
2. Öffnen Sie die ADSI-Bearbeitung: Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **ADSI-Bearbeitung**.
    
    > [!TIP]
    > Klicken Sie alternativ auf **Start**und dann auf **Ausführen**, geben Sie **Adsiedit. msc** ein, um die ADSI-Bearbeitung zu starten.
  
3. Klicken Sie in der MMC-Struktur (Microsoft Management Console) auf ADSI-Bearbeitung, wenn Sie noch nicht ausgewählt ist.
    
4. Klicken Sie im Menü **Aktion** auf **Verbinden mit**.
    
5. Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus und klicken Sie dann auf **OK**.
    
6. Suchen Sie unter dem Schemacontainer nach CN=ms-RTC-SIP-SchemaVersion. Wenn dieses Objekt vorhanden ist und der Wert des **rangeUpper** -Attributs 1150 ist und der Wert des **rangeLower** -Attributs 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder die Werte der **rangeUpper** -und **rangeLower** -Attribute nicht wie angegeben sind, wurde das Schema nicht geändert oder nicht repliziert.
    
> [!NOTE]
> Wenn die Überprüfung der Replikation des Schemas noch keine erfolgreiche Replikation anzeigt, warten Sie ungefähr 15 Minuten, und überprüfen Sie dann erneut. Die Active Directory-Replikation basiert auf einem lockeren Konsistenz Modell, und es kann einige Replikations Latenzen auf der Grundlage einer Reihe von Faktoren auf dem Server und der Infrastruktur auftreten. 
  

