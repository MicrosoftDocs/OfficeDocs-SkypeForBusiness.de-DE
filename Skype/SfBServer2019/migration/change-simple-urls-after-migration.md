---
title: Ändern einfacher URLs nach der Migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype für Business Server unterstützt einfache URLs.
ms.openlocfilehash: 02f4cc729a50459a8125e216265b935d557007c6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892709"
---
# <a name="change-simple-urls-after-migration"></a>Ändern einfacher URLs nach der Migration

Skype für Business Server unterstützt drei einfache URLs:
  
- **Erfüllen** wird als Basis-URL für alle Konferenzen in der Website oder Ihrer Organisation verwendet. Mit den einfachen URLs sind Links zu Besprechungen teilnehmen, die einfach zu verstehen und leicht zu kommunizieren und zu verteilen. 
    
- **Zugriffsnummer für Einwahl** ermöglicht den Zugriff auf die Webseite mit Einwahl Einstellungen. Die Zugriffsnummer für Einwahl einfache URL ist in allen besprechungseinladungen enthalten, damit Benutzer, die in die Besprechung einwählen möchten die erforderlichen Telefonnummer und PIN-Informationen zugreifen können. 
    
- **Admin** ermöglicht schnellen Zugriff auf die Skype Business Server-Systemsteuerung. Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation. 
    
Nach der Migration zu Skype für Business Server, müssen Ihnen bekannt sein wie die Änderung Ihrer DNS-Einträgen und Zertifikaten für einfache URLs auswirkt. Wenn derzeit in der Topologie der Vorgängerversion Skype für Business Server Director bleibt, sind keine Änderungen an der einfachen URLs erforderlich. Wenn die Skype für Business Server Director nach der Migration aus der Topologie entfernt wird, müssen die einfache URL-DNS-Einträge aktualisiert werden, um eines der Skype für Business Server-Pools zu verweisen. Wenn Sie einen einfachen URL-Name ändern, müssen Sie Enable-CsComputer auf jedem Director und Front-End-Server, um die Änderung zu registrieren ausführen.

## <a name="to-update-the-meet-simple-url"></a>So aktualisieren Sie die einfache Meet-URL

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste im obersten Knotens **Skype für Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
2. Wählen Sie die **Einfache URLs** im linken Bereich, klicken Sie dann unter **Besprechung URLs:** wählen Sie die URL erfüllen, und klicken Sie dann auf **URL bearbeiten**.
    
3. Aktualisieren Sie die URL auf den gewünschten Wert ein, und klicken Sie dann auf **OK** , um die bearbeitete URL zu speichern. 
    
## <a name="to-update-the-admin-simple-url"></a>So aktualisieren Sie die einfache Admin-URL

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste im obersten Knotens **Skype für Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
2. Wählen Sie im linken Bereich, klicken Sie dann unten im Feld **URL für administrativen Zugriff** **Einfache URLs** aus, geben Sie die einfache URL für administrativen Zugriff auf die Skype Business Server-Systemsteuerung aus, und klicken Sie dann auf **OK**.
    
   > [!TIP]
   > Es wird empfohlen, die einfachstmögliche URL als Verwaltungs-URL zu verwenden. Die einfachste Option ist https://admin. <em> \<Domäne\></em>. 
  
## <a name="see-also"></a>Siehe auch

[DNS-Anforderungen für einfache URLs in Skype für Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
