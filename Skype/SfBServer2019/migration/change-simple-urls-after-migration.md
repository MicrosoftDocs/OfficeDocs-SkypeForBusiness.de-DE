---
title: Ändern einfacher URLs nach der Migration
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server unterstützt einfache URLs.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753905"
---
# <a name="change-simple-urls-after-migration"></a>Ändern einfacher URLs nach der Migration

Skype for Business Server unterstützt drei einfache URLs:
  
- **Meet**: Dient als Basis-URL für alle Konferenzen, die am Standort oder in der Organisation abgehalten werden. Mit der einfachen Meet-URL sind Links für den Besprechungsbeitritt einfach zu verstehen, leicht zu kommunizieren und zu verteilen. 
    
- **Dial-in**: Ermöglicht den Zugriff auf die Webseite mit den Einstellungen für eine Einwahlkonferenz. Die einfache Dial-in-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben. 
    
- Der **Administrator** ermöglicht den schnellen Zugriff auf die Skype for Business Server-Systemsteuerung. Die einfache Admin-URL wird innerhalb Ihrer Organisation verwendet. 
    
Nach der Migration zu Skype for Business Server müssen Sie wissen, wie sich die Änderung auf Ihre DNS-Einträge und Zertifikate für einfache URLs auswirkt. Wenn der Legacy Skype for Business Server Director in der Topologie weiterhin verwendet wird, sind keine Änderungen an ihren einfachen URLs erforderlich. Wenn der Skype for Business Server Director nach der Migration aus der Topologie entfernt wird, müssen die DNS-Einträge für einfache URLs so aktualisiert werden, dass Sie auf einen der Skype for Business Server-Pools verweist. Bei jeder Namensänderung für eine einfache URL müssen Sie jedoch das Cmdlet "Enable-CsComputer" auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

## <a name="to-update-the-meet-simple-url"></a>So aktualisieren Sie die einfache Meet-URL

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **Skype for Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
2. Wählen Sie im linken Bereich **einfache URLs** und dann unter **Besprechungs-URLs:** wählen Sie die URL "Meet" aus, und klicken Sie dann auf **URL bearbeiten**.
    
3. Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie auf **OK**, um die bearbeitete URL zu speichern. 
    
## <a name="to-update-the-admin-simple-url"></a>So aktualisieren Sie die einfache Admin-URL

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **Skype for Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
2. Wählen Sie **einfache URLs** im linken Bereich aus, und geben Sie dann unterhalb des Felds **Administrative Zugriffs-URL** die einfache URL ein, die Sie für den administrativen Zugriff auf Skype for Business Server Systemsteuerung wünschen, und klicken Sie dann auf **OK**.
    
   > [!TIP]
   > Es wird empfohlen, eine möglichst einfache URL als Admin-URL zu verwenden. Die einfachste Option ist https://admin . <em>\<domain\></em> . 
  
## <a name="see-also"></a>Siehe auch

[DNS-Anforderungen für einfache URLs in Skype for Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
