---
title: Migrieren von Einwahl Zugriffsnummern
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Migrieren von Einwahlnummern Zahlen zu Skype für Business Server 2019 erforderlich sind, mit dem Cmdlet Move-CsApplicationEndpoint die Kontaktobjekte zu migrieren. Während der Vorversion installieren und Skype für Business Server 2019 Koexistenz Zeitraum Verhalten sich Einwahlnummern Zahlen, die Sie in Skype für Business Server 2019 erstellt haben ähnlich wie DFÜ-Zugriff Zahlen, die Sie in der Vorversion installieren, erstellen Sie wie beschrieben in diesem Abschnitt.
ms.openlocfilehash: 62d2d4f34f109c265a72a92283082601bd92b40b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027725"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrieren von Einwahl Zugriffsnummern

Migrieren von Einwahlnummern Zahlen zu Skype für Business Server 2019 erforderlich sind, mit dem Cmdlet **Move-CsApplicationEndpoint** die Kontaktobjekte zu migrieren. Während der Vorversion installieren und Skype für Business Server 2019 Koexistenz Zeitraum Verhalten sich Einwahlnummern Zahlen, die Sie in Skype für Business Server 2019 erstellt haben ähnlich wie DFÜ-Zugriff Zahlen, die Sie in der Vorversion installieren, erstellen Sie wie beschrieben in diesem Abschnitt. 
  
DFÜ-Zugriff Zahlen, die Sie in der Vorgängerversion erstellt haben, installieren Sie jedoch verschoben und Skype für Business Server 2019 oder erstellten in Skype für Business Server 2019 vor, während oder nach der Migration, weisen folgende Merkmale auf:
  
- In Office Communications Server 2007 R2-besprechungseinladungen und die Seite mit der DFÜ-Zugriff nicht angezeigt.
    
- Klicken Sie auf der Vorversion Install-besprechungseinladungen und auf die Seite mit der DFÜ-Zugriff angezeigt.
    
- Für Business Server 2019-besprechungseinladungen und auf die Seite mit der DFÜ-Zugriff auf Skype angezeigt.
    
- Nicht angezeigt oder im Verwaltungstool von Office Communications Server 2007 R2 geändert werden.
    
- Können angezeigt und in der Vorversion Install-Systemsteuerung und in der Vorversion Install-Verwaltungsshell geändert werden.
    
- Können angezeigt und in der Skype Business Server 2019-Systemsteuerung und Skype für Business Server 2019-Verwaltungsshell geändert werden.
    
- Können innerhalb der Region neu sequenziert werden mithilfe des Cmdlets Set-CsDialinConferencingAccessNumber mit dem Parameter Priority.
    
Sie müssen die Migration abgeschlossen Einwahl Zugriffsnummern, die auf der Vorgängerversion zeigen Pool installieren, bevor Sie den Vorversion Install-Pool außer Betrieb nehmen. Eingehende Anrufe an die Zugriffsnummern schlägt fehl, wenn Sie nicht über DFÜ-Zugriff der Migration wie im folgenden Verfahren beschrieben durchführen.
  
> [!IMPORTANT]
> Sie müssen dieses Verfahren vor der Außerbetriebnahme der Vorversion Install Pools ausführen. 
  
> [!NOTE]
> Es wird empfohlen, das Netzwerkauslastung möglichst gering ist, für den Fall, dass es eine kurzen Dienstausfall wird Einwahl Zugriffsnummern verschieben. 
  
## <a name="to-identify-and-move-dial-in-access-numbers"></a>So identifizieren und Einwahl Zugriffsnummern verschieben

1. Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.
    
2. Um jede Zugriffsnummer für Einwahl-Zugriffsnummer in einen auf Skype für Business Server 2019 gehosteten Pool verschieben, über die Befehlszeile ausführen: 
    
  ```
  Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
  
  ```

3. Öffnen von Skype Business Server-Systemsteuerung.
    
4. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.
    
5. Klicken Sie auf der Registerkarte **Zugriffsnummer für Einwahl** . 
    
6. Stellen Sie sicher, dass keine Zugriffsnummer für Einwahl-Zugriffsnummern für den Pool der Vorgängerversion installieren zurückbleiben, aus dem Sie migrieren.
    
    > [!NOTE]
    > Wenn alle Einwahl Zugriffsnummern auf die Skype für Business Server 2019 Pool zeigen, können Sie dann den Vorversion installieren Pool außer Betrieb nehmen. 
  
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Überprüfen der DFÜ-Zugriff der Migrations mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich von einem Benutzerkonto, dem die Rolle **"CsUserAdministrator** " oder **der csadministrator** zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz**.
    
4. Klicken Sie auf der Registerkarte **Zugriffsnummer für Einwahl** . 
    
5. Stellen Sie sicher, dass alle Einwahlnummern Zahlen in der auf Skype für Business Server 2019 gehosteten Pool migriert werden.
    
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Überprüfen der DFÜ-Zugriff der Migrations mithilfe von Skype für Business Server-Verwaltungsshell

1. Öffnen Sie Skype für Business Server-Verwaltungsshell.
    
2. Um alle zurücksenden migriert die Zugriffsnummern für einwahlkonferenzen über die Befehlszeile ausführen:
    
  ```
  Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
  ```

3. Stellen Sie sicher, dass alle Einwahlnummern Zahlen in der auf Skype für Business Server 2019 gehosteten Pool migriert werden.
    

