---
title: Allgemeine Einstellungen für externe Anwendungen – Erweiterung
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
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Befolgen Sie diese Anweisungen, um die Eigenschaften für einen vertrauenswürdigen Anwendungsserver zu bearbeiten, der bereits definiert wurde.
ms.openlocfilehash: 55f6bfee68370f8f341080e54953120e48f628f8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804765"
---
# <a name="external-application-general-settings-expander"></a>Allgemeine Einstellungen für externe Anwendungen – Erweiterung
 
Befolgen Sie diese Anweisungen, um die Eigenschaften für einen vertrauenswürdigen Anwendungsserver zu bearbeiten, der bereits definiert wurde.
  
Zwei Abschnitte können geändert werden:
  
> Allgemeine Einstellungen
> 
> Einstellungen für nächsten Hop
    
## <a name="general-settings"></a>Allgemeine Einstellungen

Sie können den aktuellen FQDN (Fully Qualified Domain Name) für den Pool vertrauenswürdiger Anwendungsserver ändern. Bearbeiten Sie den vollqualifizierten Namen für den Pool. Der DNS-A-Eintrag (Host) muss für den neuen Eintrag vorhanden sein, ehe sich Clients oder Server mit dem Pool mit dem neuen Namen verbinden können.
  
Wählen Sie **Replikation von Konfigurationsdaten in diesen Pool aktivieren** aus, wenn die Replikation von Konfigurationsdaten in diesen Pool erforderlich sein sollte. Deaktivieren Sie dieses Kontrollkästchen, wenn die Konfigurationsdaten nicht repliziert werden sollen.
  
## <a name="next-hop-settings"></a>Einstellungen für nächsten Hop

Sie können den nächsten Hopserver des Pools der vertrauenswürdigen Anwendungsserver angeben, indem Sie in der Dropdownliste den definierten Front-End-Pool der Enterprise Edition oder den Front-End-Server der Standard Edition auswählen. Ein Director oder Director-Pool kann nicht als nächster Hop für einen vertrauenswürdigen Anwendungsserver ausgewählt werden und wird daher nicht in der Liste aufgeführt.
  


Klicken Sie **auf "OK",** um die Änderungen zu akzeptieren und zu speichern. Klicken Sie auf **Abbrechen**, um Ihre Änderungen zu verwerfen und die Eigenschaftenseite zu schließen.
  

