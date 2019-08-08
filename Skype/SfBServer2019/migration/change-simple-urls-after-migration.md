---
title: Ändern einfacher URLs nach der Migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server unterstützt einfache URLs.
ms.openlocfilehash: 806003a2639d3861c066248657521ceb58a4e986
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239493"
---
# <a name="change-simple-urls-after-migration"></a>Ändern einfacher URLs nach der Migration

Skype for Business Server unterstützt drei einfache URLs:
  
- **Meet** wird als Basis-URL für alle Konferenzen auf der Website oder Organisation verwendet. Mit der einfachen URL für Besprechungen sind Links zu Besprechungen einfach zu verstehen und einfach zu kommunizieren und zu verteilen. 
    
- **Einwahl** ermöglicht den Zugriff auf die Webseite für Einwahlkonferenzeinstellungen. Die Einwahl einfache URL ist in allen Besprechungseinladungen enthalten, damit Benutzer, die sich in die Besprechung einwählen möchten, auf die erforderlichen Telefonnummern und PIN-Informationen zugreifen können. 
    
- Der **Administrator** ermöglicht den schnellen Zugriff auf das Skype for Business Server-Control Panel. Die einfache Admin-URL dient der internen Verwendung in Ihrer Organisation. 
    
Nach der Migration zu Skype for Business Server müssen Sie wissen, wie sich die Änderung auf Ihre DNS-Einträge und Zertifikate für einfache URLs auswirkt. Wenn der Legacy-Manager von Skype for Business Server in der Topologie weiterhin verwendet wird, sind keine Änderungen an ihren einfachen URLs erforderlich. Wenn der Skype for Business Server-Director nach der Migration aus der Topologie entfernt wird, müssen die einfachen URL-DNS-Einträge aktualisiert werden, sodass Sie auf einen der Skype for Business Server-Pools verweisen. Wenn Sie jedoch einen einfachen URL-Namen ändern, müssen Sie Enable-CsComputer auf jedem Director und Front-End-Server ausführen, um die Änderung zu registrieren.

## <a name="to-update-the-meet-simple-url"></a>So aktualisieren Sie die einfache URL für Besprechungen

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **von Skype for Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
2. Wählen Sie im linken Bereich und dann unter Besprechungs- **URLs** **einfache URLs** aus: Wählen Sie die URL erfüllen aus, und klicken Sie dann auf **URL bearbeiten**.
    
3. Aktualisieren Sie die URL auf den gewünschten Wert, und klicken Sie dann auf **OK** , um die bearbeitete URL zu speichern. 
    
## <a name="to-update-the-admin-simple-url"></a>So aktualisieren Sie die einfache Administrator-URL

1. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den obersten Knoten **von Skype for Business Server**, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
2. Wählen Sie im linken Bereich **einfache URLs** aus, und geben Sie dann unter **Administratorzugriff-URL** die einfache URL ein, die Sie für den administrativen Zugriff auf die Skype for Business Server-Systemsteuerung benötigen, und klicken Sie dann auf **OK**.
    
   > [!TIP]
   > Es wird empfohlen, die einfachstmögliche URL als Verwaltungs-URL zu verwenden. Die einfachste Option ist https://admin. <em> \<Domäne\></em>aus. 
  
## <a name="see-also"></a>Siehe auch

[DNS-Anforderungen für einfache URLs in Skype for Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
