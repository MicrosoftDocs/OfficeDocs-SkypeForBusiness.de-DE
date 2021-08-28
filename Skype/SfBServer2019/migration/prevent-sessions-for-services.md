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
ms.localizationpriority: medium
description: Sie können die Systemsteuerung für Legacyinstallationen verwenden, um neue Sitzungen für alle Legacydienste zu verhindern, die auf einem bestimmten Computer ausgeführt werden, oder um neue Sitzungen für einen bestimmten Legacydienst zu verhindern.
ms.openlocfilehash: 2f65d9453eab4548d9b4b94a5c6d38673d3ebd54
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595009"
---
# <a name="prevent-sessions-for-services"></a>Verhindern von Sitzungen für Dienste

Sie können die Systemsteuerung für Legacyinstallationen verwenden, um neue Sitzungen für alle Legacydienste zu verhindern, die auf einem bestimmten Computer ausgeführt werden, oder um neue Sitzungen für einen bestimmten Legacydienst zu verhindern.
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a>So verhindern Sie neue Sitzungen für Dienste auf einem Computer

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server 2019 bereitgestellt haben.
    
2. Öffnen Sie Skype for Business Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
    
4. Sortieren oder durchsuchen Sie auf der Seite **Status** die Liste, um den Computer zu ermitteln, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten. Klicken Sie anschließend auf den Computer. 
    
5. Klicken Sie auf **Aktion**.
    
6. Klicken Sie auf **Neue Sitzungen für alle Dienste verhindern**.
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a>So verhindern Sie neue Sitzungen für einen bestimmten Dienst

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server 2019 bereitgestellt haben.
    
2. Öffnen Sie Skype for Business Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.
    
4. Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer. 
    
5. Klicken Sie auf **Eigenschaften**.
    
6. Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.
    
7. Klicken Sie auf **Aktion**.
    
8. Klicken Sie auf **Neue Sitzungen für Dienst verhindern**.
    
9. Klicken Sie auf **Schließen**.
    

