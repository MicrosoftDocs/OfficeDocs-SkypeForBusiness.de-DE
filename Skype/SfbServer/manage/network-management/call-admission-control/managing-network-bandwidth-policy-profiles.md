---
title: Verwalten von Netzwerkbandbreitenrichtlinienprofilen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Verwenden Sie die Verfahren in diesem Artikel zum Anzeigen, Erstellen, Ändern oder Löschen von Richtlinienprofilen für die Netzwerkbandbreite.
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816445"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>Verwalten von Richtlinienprofilen für die Netzwerkbandbreite in Skype for Business Server

Verwenden Sie die Verfahren in diesem Artikel zum Anzeigen, Erstellen, Ändern oder Löschen von Richtlinienprofilen für die Netzwerkbandbreite.

## <a name="view-network-bandwidth-policy-profile-information"></a>Anzeigen von Informationen zum Netzwerkbandbreitenrichtlinienprofil

Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren. In Skype for Business Server können Bandbreiteneinschränkungen nur für Audio- und Videodaten zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen. Sie können die Skype for Business Server-Systemsteuerung verwenden, um ein Containerprofil für diese Richtlinien zu erstellen, zu ändern oder zu löschen. Jedes Bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet werden. Verwenden Sie die folgenden Verfahren, um ein Bandbreitenrichtlinienprofil anzuzeigen. 

### <a name="to-view-a-bandwidth-policy-profile"></a>So zeigen Sie ein Bandbreitenrichtlinienprofil an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie **auf der** Seite "Bandbreitenrichtlinie" auf das Bandbreitenrichtlinienprofil, das Sie anzeigen möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zum Netzwerkbandbreitenrichtlinienprofil mithilfe Windows PowerShell Cmdlets

Netzwerkbandbreitenprofile können mithilfe des cmdlets Windows PowerShell und Get-CsNetworkBandwidthPolicyProfile angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell. 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>So zeigen Sie Informationen zum Netzwerkbandbreitenrichtlinienprofil an

  - Geben Sie zum Anzeigen von Informationen zu allen Netzwerkbandbreitenrichtlinienprofilen den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


Weitere Informationen finden Sie in dem Hilfethema zum [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)-Cmdlet.


## <a name="create-or-modify-bandwidth-policy-profiles"></a>Erstellen oder Ändern von Bandbreitenrichtlinienprofilen

Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren. In Skype for Business Server können Bandbreiteneinschränkungen nur für Audio- und Videodaten zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen. Sie können die Skype for Business Server-Systemsteuerung verwenden, um ein Containerprofil für diese Richtlinien zu erstellen, zu ändern oder zu löschen. Jedes Bandbreitenrichtlinienprofil kann mindestens einem Netzwerkstandort zugeordnet werden. Erstellen oder ändern Sie mithilfe der folgenden Verfahren ein Bandbreitenrichtlinienprofil. 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>So erstellen Sie ein neues Bandbreitenrichtlinienprofil

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Bandbreitenrichtlinie".**

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf **Neu**.

5.  Geben Sie im Abschnitt **Neues Bandbreitenrichtlinienprofil** im Feld **Name** einen Namen ein. Dieser Name muss eindeutig sein.

6.  Geben Sie im Feld **Audiolimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für alle Audioverbindungen in KBit/s fest.

7.  Geben Sie im Feld **Audiositzungslimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für eine einzelne Audioverbindung in KBit/s fest. Dieser Wert muss auf mindestens 40 festgelegt werden.

8.  Geben Sie im Feld **Videolimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für alle Videoverbindungen in KBit/s fest.

9.  Geben Sie im Feld **Videositzungslimit** einen numerischen Wert ein. Dieser Wert legt die maximale Bandbreite für eine einzelne Videoverbindung in KBit/s fest. Dieser Wert muss auf mindestens 100 festgelegt werden.

10. (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Bandbreitenrichtlinienprofil ein, die nicht durch den Namen allein vermittelt werden können.

11. Klicken Sie auf **Commit**.

    > [!NOTE]  
    > Beim Erstellen eines neuen Bandbreitenrichtlinienprofils werden die Bandbreiteneinschränkungen nicht automatisch erzwungen. Sie müssen das Richtlinienprofil zunächst einem Standort zuordnen. 


### <a name="to-modify-a-bandwidth-policy-profile"></a>So ändern Sie ein Bandbreitenrichtlinienprofil

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Bandbreitenrichtlinie".**

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das Bandbreitenrichtlinienprofil, das geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie **auf der Seite "Bandbreitenrichtlinienprofil** bearbeiten" die Felder nach Bedarf (Weitere Informationen finden Sie unter So erstellen Sie ein neues Bandbreitenrichtlinienprofil). [](#to-create-a-new-bandwidth-policy-profile)

7.  Klicken Sie auf **Commit**.

    > [!NOTE]  
    > Beim Ändern des Bandbreitenrichtlinienprofils werden die Bandbreiteneinschränkungen aller Netzwerkstandorte, die diesem Bandbreitenrichtlinienprofil zugeordnet sind, umgehend aktualisiert.

  
## <a name="delete-network-bandwidth-policy-profiles"></a>Löschen von Richtlinienprofilen für die Netzwerkbandbreite

Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren. In Skype for Business Server können Bandbreiteneinschränkungen nur für Audio- und Videodaten zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen. Sie können die Skype for Business Server-Systemsteuerung verwenden, um ein Containerprofil für diese Richtlinien zu erstellen, zu ändern oder zu löschen. Mit den folgenden Verfahren können Sie Richtlinienprofile für Netzwerkbandbreiten löschen. 

### <a name="to-delete-a-bandwidth-policy-profile"></a>So löschen Sie ein Richtlinienprofil für die Bandbreite

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Bandbreitenrichtlinie".**

4.  Klicken Sie auf der Seite **Bandbreitenrichtlinie** auf das Richtlinienprofil der Bandbreite, das Sie löschen möchten.

    > [!NOTE]  
    > Sie können auch mehrere Profile auf einmal löschen. Drücken Sie dazu die STRG-TASTE, und halten Sie sie gedrückt, während Sie mit der Maus auf die einzelnen Profile klicken. Wenn Sie alle Profile auswählen möchten, klicken Sie einfach im Menü **Bearbeiten** auf **Alle auswählen**.

5.  Abschließend klicken Sie im Menü **Bearbeiten** auf **Löschen**.
   

    > [!WARNING]  
    > Richtlinienprofile für Bandbreiten, die mit einem Netzwerkstandort verknüpft sind, können nicht ohne Weiteres gelöscht werden. In diesem Fall müssen Sie zuerst die Verknüpfung mit dem Netzwerkstandort aufheben, bevor Sie das Profil löschen können. 


## <a name="see-also"></a>Siehe auch

[Verwalten der Anrufsteuerung für Standorte](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

