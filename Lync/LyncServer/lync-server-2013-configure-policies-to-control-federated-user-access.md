---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs'
TOCTitle: Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398359(v=OCS.15)
ms:contentKeyID: 49294027
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Wenn Sie Richtlinien zur Unterstützung der Kommunikation mit Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von Partnerdomänen. Sie können eine oder mehrere Richtlinien für den Zugriff externer Benutzer konfigurieren und steuern, ob Benutzer von Partnerdomänen mit Ihren Lync Server 2013-Benutzern zusammenarbeiten können. Zum Steuern des Zugriffs durch Partnerbenutzer können Sie Richtlinien auf globaler Ebene sowie Standort- und Benutzerebene konfigurieren. Lync Server-Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien, und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.


> [!NOTE]
> Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch Partnerbenutzer konfigurieren, wenn Sie den Partnerverbund für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien treten jedoch erst dann in Kraft, wenn der Partnerverbund für Ihre Organisation aktiviert ist. Ausführliche Informationen zum Aktivieren des Partnerverbunds finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013</A> in der Bereitstellungs- oder der Betriebdokumentation. Wenn Sie eine Benutzerrichtlinie zur Steuerung des Zugriffs durch Partnerbenutzer angeben, gilt die Richtlinie zudem nur für Benutzer, die für Lync Server 2013 aktiviert und für die Verwendung der Richtlinie konfiguriert wurden.



## So konfigurieren Sie eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff** .

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:
    
      - Um die globale Richtlinie für die Unterstützung des Zugriffs durch Partnerbenutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen** .
    
      - Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie** . Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK** .
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie** . Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name** , der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableFederatedUsers** für eine Benutzerrichtlinie, welche die Kommunikation für Benutzer aus Partnerdomänen ermöglicht).
    
      - Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen** .

5.  (Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren** , um den Zugriff durch Partnerbenutzer für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren** , um den Zugriff durch Partnerbenutzer für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit** .

Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerverbund in Ihrer Organisation aktivieren. Ausführliche Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).

Handelt es sich um eine Benutzerrichtlinie, müssen Sie die Richtlinie auch auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen. Ausführliche Informationen finden Sie unter [Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).

## So konfigurieren Sie eine vorhandene Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    
    Nachstehend finden Sie ein Beispiel für einen Befehl, mit dem die globale Richtlinie für den Zugriff durch Partnerbenutzer, der Zugriff auf die XMPP-Domäne, der Zugriff für Remotebenutzer sowie der Zugriff für öffentliche Anbieter auf "aktiviert" festgelegt und die Audio- und Videounterstützung für entsprechende öffentliche Anbieter zugelassen wird:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    

    > [!TIP]
    > Der Parameter „EnablePublicCloudAudioVideoAccess“ weist keine entsprechende Auswahl in Lync Server-Systemsteuerung auf.



## So erstellen Sie eine neue Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein:
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Nachstehend finden Sie ein Beispiel für das Erstellen einer neuen Standortrichtlinie:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

## So löschen Sie eine Richtlinie mithilfe von Windows PowerShell zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen oder setzen diese zurück

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    Nachstehend finden Sie ein Beispiel für das Zurücksetzen der globalen Richtlinie (die Einstellungen der globalen Richtlinie können zwar entfernt, die Richtlinie selbst kann jedoch nicht gelöscht werden):
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    Geben Sie den folgenden Befehl ein, um eine Standortrichtlinie zu löschen:
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Mit diesem Befehl wird die Standortrichtlinie "Redmond" gelöscht. Geben Sie den folgenden Befehl ein, um die Richtlinie "UserEAPPolicy" zu löschen:
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

## Siehe auch

#### Aufgaben

[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  

#### Weitere Ressourcen

[Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

