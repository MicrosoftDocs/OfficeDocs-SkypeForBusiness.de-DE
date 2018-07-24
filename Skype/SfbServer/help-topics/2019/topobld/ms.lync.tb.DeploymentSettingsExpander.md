---
title: Bereitstellungseinstellungen – Erweiterung
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie können die Eigenschaften für eine vorhandene Bereitstellung mit den folgenden Abschnitten bearbeiten:'
ms.openlocfilehash: dbcde83b3fbdc168c3b4d75ba9543205fd07f9e9
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21068475"
---
# <a name="deployment-settings-expander"></a>Bereitstellungseinstellungen – Erweiterung
 
Sie können die Eigenschaften für eine vorhandene Bereitstellung mit den folgenden Abschnitten bearbeiten:
  
- SIP-Domäne
    
- Einfache URLs
    
- Zentraler Verwaltungsserver
    
## <a name="sip-domain"></a>SIP-Domäne

Geben Sie zum Ändern der **Standard-SIP-Domäne** den neuen Domänennamen ein. 
  
Geben Sie zum Hinzufügen**** weiterer unterstützter SIP-Domänen den Namen der Domäne ein, die hinzugefügt werden soll. Klicken Sie auf **Hinzufügen**, um den neuen SIP-Domänennamen (Session Initiation Protocol) zu übernehmen.
  
Wählen Sie zum Ändern eines vorhandenen zusätzlichen SIP-Domänennamens den Domänennamen aus und nehmen Sie im Textfeld Änderungen vor. Klicken Sie auf **Aktualisieren**, um die Änderung zu übernehmen.
  
Wählen Sie zum Entfernen eines definierten zusätzlichen SIP-Domänennamens den Domänennamen und klicken Sie dann auf **Entfernen**.
  
Klicken Sie, nachdem Sie alle Änderungen auf der Seite „Eigenschaften bearbeiten“ vorgenommen haben, auf **OK**, um die Änderungen zu speichern. Klicken Sie auf **Abbrechen**, um Änderungen zu verwerfen.
  
## <a name="simple-urls"></a>Einfache URLs

Zum Ändern oder Definieren der einfachen URLs müssen Sie bestimmen, welche der drei einfachen URLs Sie bearbeiten oder ändern möchten. Zur Auswahl stehen die Telefonzugriffs-URL, die Besprechungs-URL und die URL für den administrativen Zugriff.
  
Wählen Sie zum Ändern der Telefonzugriffs-URL oder der Besprechungs-URL die zu ändernde URL aus. Klicken Sie auf **URL bearbeiten**. Bearbeiten Sie anschließend die URL, und klicken Sie auf **OK**, um die URL zu speichern. Klicken Sie auf **Abbrechen**, um die Änderungen zu verwerfen.
  
Klicken Sie auf **Hinzufügen**, um eine neue URL hinzuzufügen. Geben Sie im Dialogfeld **Einfache URL hinzufügen** die URL an und klicken Sie auf **OK**, um die URL zu speichern. Aktivieren Sie **Als aktive URL für die ausgewählte Domäne festlegen**, wenn die neue URL als aktive URL festgelegt werden soll. Klicken Sie auf **Abbrechen**, um sämtliche Änderungen zu verwerfen.
  
Wählen Sie zum Festlegen einer anderen URL als aktive URL (gekennzeichnet durch ein grünes Häkchen neben der URL) die betreffende URL, und klicken Sie dann auf **Aktivieren**.
  
> [!NOTE]
> Für jede SIP-Domäne kann nur eine aktive URL vorhanden sein. 
  
Wenn Sie eine URL entfernen müssen, wählen Sie sie aus und klicken Sie dann auf **Entfernen**.
  
> [!CAUTION]
> Lesen Sie die Informationen auf der Dialogfeldseite mit den Einstellungen einfacher URLs sorgfältig durch. Das Entfernen einer Besprechungs-URL kann dazu führen, dass auf von Benutzern geplante Besprechungen kein Zugriff mehr möglich ist. Erwägen Sie die Beibehaltung der vorhandenen URL, nachdem Sie die neue Besprechungs-URL als aktiv festgelegt haben. Sobald Sie sicher sind, dass keine Benutzer mehr die alte Besprechungs-URL verwenden, können Sie sie unbesorgt entfernen. 
  
Zum Bearbeiten oder Ändern der URL für den administrativen Zugriff müssen Sie den Eintrag bearbeiten.
  
Klicken Sie, nachdem Sie alle Änderungen auf der Seite „Eigenschaften bearbeiten“ vorgenommen haben, auf **OK**, um die Änderungen zu speichern. Klicken Sie auf **Abbrechen**, um Änderungen zu verwerfen.
  
## <a name="central-management-server"></a>Zentraler Verwaltungsserver

Der zentrale Verwaltungsserver kann aus einem definierten Front-End-Pool in einen anderen verschoben werden. Wählen Sie zum Ändern des Speicherorts des zentralen Verwaltungsservers den Front-End-Pool in der Dropdownliste unter **Front-End-Server, auf dem der zentrale Verwaltungsserver installiert werden soll**. Ein Front-End-Server kann ein Front-End-Pool der Enterprise Edition oder ein Front-End-Server der Standard Edition sein.
  
> [!IMPORTANT]
> Nachdem Sie den zentralen Verwaltungsspeicher für die Infrastruktur definiert, veröffentlicht und bereitgestellt haben, kann der Speicherort des zentralen Verwaltungsspeichers nur über einen externen Vorgang in einen anderen Front-End-Pool verschoben werden. 
  
Ausführliche Informationen zum Verschieben des zentralen Verwaltungsspeichers finden Sie unter [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps) in der Windows PowerShell-Cmdlet-Referenz.
  

Ausführliche Informationen zum Definieren und Konfigurieren dieser Einstellungen finden Sie unter [definieren und Konfigurieren der Topologie](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx).
  

