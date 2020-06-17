---
title: Verhindern von Sitzungen für Dienste
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
description: Sie können die Systemsteuerung "Legacy installs" verwenden, um neue Sitzungen für alle auf einem bestimmten Computer ausgeführten Legacy Dienste zu verhindern oder um neue Sitzungen für einen bestimmten Legacy Dienst zu verhindern.
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752287"
---
# <a name="prevent-sessions-for-services"></a>Verhindern von Sitzungen für Dienste

Sie können die Systemsteuerung "Legacy installs" verwenden, um neue Sitzungen für alle auf einem bestimmten Computer ausgeführten Legacy Dienste zu verhindern oder um neue Sitzungen für einen bestimmten Legacy Dienst zu verhindern.
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a>So verhindern Sie neue Sitzungen für Dienste auf einem Computer

1. Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server 2019 bereitgestellt haben.
    
2. Öffnen Sie Skype for Business Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
    
4. Sortieren oder durchsuchen Sie auf der Seite **Status** die Liste, um den Computer zu ermitteln, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten. Klicken Sie anschließend auf den Computer. 
    
5. Klicken Sie auf **Aktion**.
    
6. Klicken Sie auf **Neue Sitzungen für alle Dienste verhindern**.
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a>So verhindern Sie neue Sitzungen für einen bestimmten Dienst

1. Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server 2019 bereitgestellt haben.
    
2. Öffnen Sie Skype for Business Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
    
4. Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer. 
    
5. Klicken Sie auf **Eigenschaften**.
    
6. Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.
    
7. Klicken Sie auf **Aktion**.
    
8. Klicken Sie auf **Neue Sitzungen für Dienst verhindern**.
    
9. Klicken Sie auf **Schließen**.
    

