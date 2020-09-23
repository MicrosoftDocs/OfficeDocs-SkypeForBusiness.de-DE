---
title: Allgemeine Einstellungen für externe Anwendungen – Erweiterung
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
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Befolgen Sie diese Anweisungen, um die Eigenschaften für einen vertrauenswürdigen Anwendungsserver zu bearbeiten, der bereits definiert wurde.
ms.openlocfilehash: 9a9ed62040724d08ebcd711551cd1ce6e831d683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218136"
---
# <a name="external-application-general-settings-expander"></a>Allgemeine Einstellungen für externe Anwendungen – Erweiterung
 
Befolgen Sie diese Anweisungen, um die Eigenschaften für einen vertrauenswürdigen Anwendungsserver zu bearbeiten, der bereits definiert wurde.
  
Zwei Abschnitte können geändert werden:
  
> Allgemeine Einstellungen
> 
> Einstellungen für nächsten Hop
    
## <a name="general-settings"></a>Allgemeine Einstellungen

Sie können den aktuellen FQDN (Fully Qualified Domain Name) für den Pool vertrauenswürdiger Anwendungsserver ändern. Bearbeiten Sie den vollqualifizierten Namen für den Pool. Der DNS-A-Eintrag (Host) muss für den neuen Eintrag vorhanden sein, ehe sich Clients oder Server mit dem Pool mit dem neuen Namen verbinden können.
  
Wählen Sie **Replikation von Konfigurationsdaten in diesen Pool aktivieren** aus, wenn die Replikation von Konfigurationsdaten in diesen Pool erforderlich sein sollte. Deaktivieren Sie dieses Kontrollkästchen, wenn die Konfigurationsdaten nicht repliziert werden sollen.
  
## <a name="next-hop-settings"></a>Einstellungen für nächsten Hop

Sie können den Server für den nächsten Hop des vertrauenswürdigen Anwendungsserver Pools angeben, indem Sie den definierten Enterprise Edition-Front-End-Pool oder Standard Edition-Front-End-Server aus der Dropdownliste auswählen. Ein Director oder Director-Pool kann nicht als nächster Hop für einen vertrauenswürdigen Anwendungsserver ausgewählt werden und wird daher nicht in der Liste aufgeführt.
  


Klicken Sie auf **OK** , um die Änderungen zu akzeptieren und zu speichern. Klicken Sie auf **Abbrechen**, um Ihre Änderungen zu verwerfen und die Eigenschaftenseite zu schließen.
  

