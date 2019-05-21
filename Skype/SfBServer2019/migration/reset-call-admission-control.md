---
title: Zurücksetzen der Anrufsteuerung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn ein Legacy-Front-End-Pool eine Anrufannahme Steuerung (CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool verschieben, bevor Sie den Legacy-Front-End-Pool entfernen können.
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307098"
---
# <a name="reset-call-admission-control"></a>Zurücksetzen der Anrufsteuerung

Wenn ein Legacy-Front-End-Pool eine Anrufannahme Steuerung (CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool verschieben, bevor Sie den Legacy-Front-End-Pool entfernen können.
  
### <a name="to-reset-cac"></a>So setzen Sie CAC zurück

1. Öffnen Sie den Topologie-Generator.
    
2. Klicken Sie mit der rechten Maustaste auf den Websiteknoten, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
3. Vergewissern Sie sich, dass unter Einstellungen für die **Anrufsteuerung**die Option **Anrufsteuerung aktivieren** aktiviert ist. 
    
4. Wählen Sie unter **Front-End-Pool zum Ausführen der Anrufannahme Steuerung (CAC)** den Skype for Business Server 2019-Pool aus, der CAC hosten soll, und klicken Sie dann auf **OK**.
    
5. Veröffentlichen Sie die Topologie.
    

