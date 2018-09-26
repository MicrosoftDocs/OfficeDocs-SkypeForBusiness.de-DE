---
title: Ändern von einfachen URLs nach der migration
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype für Business Server unterstützt einfache URLs.
ms.openlocfilehash: a67e9a8ef46b7809fdc8ce8b4eaadc2ca4720966
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028831"
---
# <a name="change-simple-urls-after-migration"></a>Ändern von einfachen URLs nach der migration

Skype für Business Server unterstützt drei einfache URLs:
  
- **Erfüllen** wird als Basis-URL für alle Konferenzen in der Website oder Ihrer Organisation verwendet. Mit den einfachen URLs sind Links zu Besprechungen teilnehmen, die einfach zu verstehen und leicht zu kommunizieren und zu verteilen. 
    
- **Zugriffsnummer für Einwahl** ermöglicht den Zugriff auf die Webseite mit Einwahl Einstellungen. Die einfache Einwahl-URL ist in allen Besprechungseinladungen enthalten, sodass Benutzer, die sich in die Besprechung einwählen möchten, Zugriff auf die erforderlichen Informationen zu Telefonnummer und PIN haben. 
    
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
    > Es wird empfohlen, die einfachstmögliche URL als Verwaltungs-URL zu verwenden. Die einfachste Option ist https://admin. _ \<Domäne\>_. 
  
## <a name="see-also"></a>Siehe auch

[DNS-Anforderungen für einfache URLs in Skype für Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
