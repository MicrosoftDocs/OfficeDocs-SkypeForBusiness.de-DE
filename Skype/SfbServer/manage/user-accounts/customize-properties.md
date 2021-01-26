---
title: Anpassen der Benutzerkontoeigenschaften für Skype for Business Server
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
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Mithilfe der Verfahren in diesem Abschnitt können Sie einzelne Benutzerkontoeigenschaften ändern.
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826265"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Anpassen der Benutzerkontoeigenschaften für Skype for Business Server
 
Mithilfe der Verfahren in diesem Abschnitt können Sie einzelne Benutzerkontoeigenschaften ändern.
  
Es gibt zwei grundlegende Vorgänge, die auf benutzerebene durchgeführt werden können:
  
- [Konfigurieren von Telefonieoptionen für ein bestimmtes Benutzerkonto](customize-properties.md#Tel_Op)
    
- [Verschieben von Benutzern in einen anderen Pool](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>Konfigurieren von Telefonieoptionen für ein bestimmtes Benutzerkonto
<a name="Tel_Op"> </a>

Sie können die Telefonieeinstellungen für einen bestimmten Benutzer anpassen (solange der einzelne Benutzer für Skype for Business Server aktiviert wurde und die Organisation Telefonie unterstützt).
  
Zu den Skype for Business Server-Benutzertelefonieoptionen gehören die folgenden:
  
- **Audio/Video deaktiviert** Der Benutzer kann keine Anrufe mit Audio und Video machen.
    
- **Nur PC zu PC** Der Benutzer kann nur Audio- oder Videoanrufe von PC zu PC machen.
    
- **Enterprise-VoIP** Der Benutzer kann die Skype for Business Server-Infrastruktur verwenden, um alle eingehenden und ausgehenden Anrufe weiterzurouten. Außerdem kann der Benutzer Anrufe von PC zu PC tätigen.
    
- **Remoteanrufsteuerung** Der Benutzer kann Skype for Business Server zum Steuern des Desktoptelefons verwenden und auch PC-zu-PC-Anrufe führen.
    
Ausführliche Informationen zum Konfigurieren der Telefonie für eine Organisation finden Sie unter ["Aktivieren](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) von Benutzern für Enterprise-VoIP in Skype for Business Server und Bereitstellen von Enterprise-VoIP in Skype for Business [Server" in](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) der Bereitstellungsdokumentation.
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.
    
5. Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie ändern möchten.
    
6. Klicken Sie im Menü **Bearbeiten** auf **Ändern**.
    
7. Führen Sie im Dialogfeld **Telefonie** die folgenden Schritte aus:
    
   - Klicken Sie zum Deaktivieren von Audio- und Videoanrufen für den Benutzer auf **Audio/Video deaktiviert**.
    
   - Wenn Sie für den Benutzer die Audiokommunikation von PC zu PC, jedoch nicht die Remoteanrufsteuerung oder Enterprise-VoIP aktivieren möchten, klicken Sie auf **Nur PC zu PC**. Geben Sie einen Wert für **Anschluss-URI** für das Telefon an, das der Benutzer für die Audiokommunikation von PC zu PC verwendet.
    
   - Klicken Sie auf Enterprise-VoIP , um die Telefonanrufe des Benutzers mithilfe der Skype for Business-Infrastruktur gemäß der Dienstklasserichtlinie weiter zu routen, einschließlich der **Pc-zu-PC-Enterprise-VoIP**. Geben Sie unter **Anschluss-URI** die Telefonnummer für Enterprise-VoIP an. Geben Sie unter **Richtlinie für Wähleinstellungen** und **VoIP-Richtlinie** die entsprechenden Richtlinien für den Benutzer an. Wählen Sie unter **Ortungsrichtlinie** das angemessene Standortprofil aus, um die Normalisierungsregeln für die Übersetzung der vom Benutzer gewählten Telefonnummern in das E.164-Format anzugeben.
    
   - Um die Remoteanrufsteuerung zu aktivieren, mit der Benutzer ihre Desktoptelefonleitung von Skype for Business Server aus steuern können, um PC-zu-PC-Anrufe und PC-zu-Telefon-Anrufe zu führen, klicken Sie auf **"Remoteanrufsteuerung".** Geben **Sie im Leitungs-URI** die Telefonnummer für die Remoteanrufsteuerung an. Der Benutzer muss über eine Verbindung mit einem Desktoptelefon und einer Nebenstellenanlage (Private Branch Exchange, PBX) für das Anrufrouting verfügen.
    
## <a name="move-users-to-another-pool"></a>Verschieben von Benutzern in einen anderen Pool
<a name="Move_Users"> </a>

Sie können die Skype for Business Server-Systemsteuerung verwenden, um Benutzer einem bestimmten Server oder Pool zuzuordnen.
  
> [!TIP]
> Das Verschieben aller vorhandenen Benutzer aus einem Quellpool mit Lync Server 2010 oder früheren Versionen in einen Skype for Business Server-Zielpool in einer komplexen Active Directory-Umgebung kann zu einer langsameren Active Directory-Replikation führen. Um dies zu vermeiden, können Sie Suchfilter verwenden, um Benutzer aus Pools mit Lync Server 2010 oder früheren Versionen separat zu verschieben, oder Sie können die Skype for Business Server-Verwaltungsshell verwenden, um Benutzer mit Cmdlets zu verschieben. Außerdem funktioniert die Filterfunktion mit Skype for Business Server-Benutzern. 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>So verschieben Sie ausgewählte Benutzer auf einen anderen Server oder Pool

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**. 
    
5. Wählen Sie in der Tabelle einen bestimmten Oder einen bestimmten Benutzer in der Liste aus. 
    
6. Klicken Sie **im Menü** "Aktion" **auf "Ausgewählte Benutzer in Pool verschieben".**
    
7. Wählen **Sie in "Benutzer** verschieben" den Pool aus, in den Sie die Benutzer im Zielregistrierungsstellenpool **verschieben möchten.**
    
8. (Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.
    
    > [!CAUTION]
    > Wenn Sie **Erzwingen** aktivieren, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (z. B. von diesem Benutzer geplante Konferenzen). Wenn Sie diese Option nicht aktivieren, werden sowohl das Benutzerkonto als auch die zugehörigen Daten verschoben. 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>So verschieben Sie alle Benutzer von einem Server oder Pool auf einen anderen Server oder in einen anderen Pool

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie auf der linken Navigationsleiste auf **Benutzer**.
    
4. Klicken Sie im Menü **Aktion** auf **Alle Benutzer in Pool verschieben**.
    
5. Wählen Sie im Abschnitt **Benutzer verschieben** unter **Quellregistrierungspool** den Pool aus, der die zu verschiebenden Benutzerkonten enthält.
    
6. Wählen Sie unter **Zielregistrierungspool** den Pool aus, in den Sie die Benutzer verschieben möchten.
    
7. (Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.
    
    > [!CAUTION]
    > Wenn Sie **Erzwingen** aktivieren, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (z. B. von diesem Benutzer geplante Konferenzen). Wenn Sie diese Option nicht aktivieren, werden sowohl das Benutzerkonto als auch die zugehörigen Daten verschoben. 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>So verschieben Sie Benutzer mithilfe eines Filters von einem Pool in einen anderen Pool

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Klicken **Sie in der** Benutzersuche auf **"Suchen"** und dann auf **"Filter hinzufügen".**
    
5. Wählen Sie in den Suchkriterien **Registrierungspool**, **Gleich** und **FQDN des aktuellen Pools** aus, und klicken Sie auf **Suchen**.
    
6. Klicken Sie im Menü **Aktion** auf **Alle Benutzer in Pool verschieben**.
    
    > [!NOTE]
    > Wenn ein Filter auf eine vorhandene Gruppe  von Benutzern angewendet wird, befindet sich die Option "Alle Benutzer in Pool verschieben" im Kontext der gefilterten Teilmenge der Benutzer, nicht aller möglichen Benutzer. 
  
7. Wählen Sie im Abschnitt **Benutzer verschieben** unter **Quellregistrierungspool** den Pool aus, der die zu verschiebenden Benutzerkonten enthält.
    
8. Wählen **Sie im Zielregistrierungsstellenpool** den Pool aus, in den Sie die Benutzer verschieben möchten.
    
9. (Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.
    
    > [!CAUTION]
    > Wenn Sie **Erzwingen** aktivieren, wird das Benutzerkonto verschoben, aber alle zugehörigen Benutzerdaten werden gelöscht (z. B. Kontakte oder von diesem Benutzer geplante Konferenzen). Wenn Sie diese Option nicht aktivieren, werden sowohl das Benutzerkonto als auch die zugehörigen Daten verschoben. 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>So verschieben Sie Benutzer mithilfe von Windows -Powershell-Cmdlets von einem Pool in einen anderen

1. Je nachdem, wie Sie Windows PowerShell (d. h. lokal oder remote) ausführen, müssen Sie sich wie folgt als Mitglied der richtigen Skype for Business Server-Administratorrollen anmelden:
    
   a. Wenn Sie die Befehle auf dem lokalen Computer ausführen (z. B. melden Sie sich direkt bei einem Front-End-Server an): Melden Sie sich bei dem Computer an, auf dem Skype for Business Server Management Shell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten, wie **unter**"Berechtigungen zum Delegieren des Setups" beschrieben.
    
   b. Wenn Sie die Befehle remote auf einem anderen Computer ausführen (beispielsweise melden Sie sich bei Ihrem Computer an und führen die Befehle remote auf einem Front-End-Server der Standard Edition aus): Melden Sie sich über ein Benutzerkonto, das der Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie **auf "Start",**"Alle **Programme",** **"Skype for Business"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
3. Zum Verschieben einzelner Benutzer verwenden Sie das Move-CsUser-Cmdlet wie folgt:
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    Dabei ist der zu verschiebende Benutzer der Benutzer Pilar Ackerman, und der Benutzer wird aus dem derzeit zugewiesenen Homepool in den Pool pool01.contoso.net
    
4. Zum Verschieben einer großen Zahl von Benutzern verwenden Sie das **Get-CsUser**-Cmdlet mit Filtern und übergeben Sie den daraus resultierenden Benutzersatz an **Move-CsUser**:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    Zusammen können die Befehle **Get-CsUser** und **Move-CsUser** Folgendes ergeben:
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


