---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer'
TOCTitle: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ552446(v=OCS.15)
ms:contentKeyID: 49293200
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Diese Dokumentation ist vorläufig und kann geändert werden. Leere Themen sind als Platzhalter enthalten.

Wenn Sie Richtlinien für die Unterstützung von XMPP (Extensible Messaging and Presence Protocol)-Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von XMPP-Verbunddomänen, nicht jedoch für Benutzer von SIP (Session Initiation Protocol)-Chatdienstanbietern (z. B. Windows Live) oder SIP-Verbunddomänen. Sie konfigurieren einen **XMPP-Verbundpartner** für jede XMPP-Verbunddomäne, die Ihren Benutzern das Hinzufügen von und Kommunizieren mit Kontakten ermöglichen soll. XMPP-Verbundpartnerrichtlinien sind nur in einem Bereich verfügbar und gelten auch dann als globale Richtlinie, wenn sie nicht als solche definiert wurden. Zum Definieren einer Richtlinie für XMPP-Verbundpartner auf globaler Ebene, Standort- oder Benutzerebene konfigurieren Sie den Richtlinienbereich, indem Sie zunächst die externe Zugriffsrichtlinie für den erforderlichen Bereich erstellen und konfigurieren. Nähere Informationen zu den Richtlinientypen, die Sie für den externen Zugriff und Verbund konfigurieren können, finden Sie unter [Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in der Betriebsdokumentation.


> [!NOTE]
> Alle Richtlinien zu <STRONG>Verbund und externem Zugriff</STRONG> werden über In-Band-Bereitstellung angewendet. Die Richtlinien, die für den Benutzer gelten, zu einem Standort gehören oder auf globaler Ebene gelten, werden während der Anmeldung an den Client kommuniziert. Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch XMPP-Verbundpartner konfigurieren, wenn Sie den XMPP-Partnerverbund für Ihre Organisation nicht aktiviert haben. Die konfigurierten Richtlinien werden jedoch nur wirksam, wenn Sie in Ihrer Konfiguration einen XMPP-Partnerverbund bereitgestellt, aktiviert und konfiguriert haben. Nähere Informationen zum Bereitstellen und Konfigurieren des XMPP-Partnerverbunds finden Sie unter <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Konfigurieren von SIP-Partnerverbünden, XMPP-Partnerverbünden und öffentlichem Chat in Lync Server 2013</A> in der Bereitstellungsdokumentation. Wenn Sie in "Externe Zugriffsrichtlinie" eine Benutzerrichtlinie zum Steuern von XMPP-Verbundpartnern festlegen, gilt die Richtlinie außerdem nur für Benutzer, die für Lync Server 2013 aktiviert und für die Verwendung der Richtlinie konfiguriert sind.



## So bearbeiten Sie eine globale Richtlinie für XMPP-Verbundpartner

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff** .

4.  Führen Sie auf der Seite **Externe Zugriffsrichtlinie** folgende Schritte an der globalen Richtlinie aus:

5.  Klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf "Details anzeigen".

6.  Geben Sie eine Beschreibung für die globale Richtlinie an (optional).

7.  Wählen Sie **Kommunikation mit Partnerbenutzern aktivieren** aus.

8.  Wählen Sie **Kommunikation mit XMPP-Partnerbenutzern aktivieren** aus.

9.  Klicken Sie auf **Commit** , um die Änderungen an der globalen Richtlinie zu speichern.

## So erstellen Sie eine Standort- oder Benutzerrichtlinie für XMPP-Verbundpartner

1.  Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie** oder **Benutzerrichtlinie** . Klicken Sie in **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK** .

2.  Geben Sie eine Beschreibung für die Standortrichtlinie an (optional).

3.  Wählen in der Standort- oder Benutzerrichtlinie **Kommunikation mit Partnerbenutzern aktivieren** .

4.  Wählen Sie **Kommunikation mit XMPP-Partnerbenutzern aktivieren** aus.

5.  Klicken Sie auf **Commit ausführen** , um Ihre Änderungen am Standort oder an der Benutzerrichtlinie zu speichern.

## So bearbeiten Sie eine vorhandene Richtlinie für XMPP-Verbundpartner

1.  Wählen Sie zum Ändern einer vorhandenen Richtlinie die entsprechende Richtlinie in der Liste aus, klicken Sie auf **Bearbeiten** und anschließend auf**Details anzeigen**.

2.  Ändern oder aktualisieren Sie die Beschreibung für die Richtlinie (optional).

3.  Aktivieren oder deaktivieren Sie dann die Option **Kommunikation mit Partnerbenutzern aktivieren** .

4.  Aktivieren oder deaktivieren Sie dann die Option **Kommunikation mit XMPP-Partnerbenutzern aktivieren** .

5.  Klicken Sie auf **Commit** , um die Änderungen an der Richtlinie zu speichern.

## So bearbeiten Sie mithilfe der Windows PowerShell eine vorhandene Richtlinie für XMPP-Verbundpartner

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Ein Beispielbefehl, der die globale Richtlinie für den Partnerbenutzerzugriff und den XMPP-Domänenzugriff aktiviert:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

## So erstellen Sie eine Standort- oder Benutzerrichtlinie für XMPP-Verbundpartner mithilfe der Windows PowerShell

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Ein Beispielbefehl, der eine Standortrichtlinie für den Standort Redmond für den Partnerbenutzerzugriff und den XMPP-Domänenzugriff aktiviert:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

## So löschen Sie mithilfe der Windows PowerShell eine vorhandene Richtlinie für XMPP-Verbundpartner

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Ein Beispielbefehl zum Löschen einer Benutzerrichtlinie:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Ein Beispielbefehl, der die globale Richtlinie auf die Standardeinstellungen zurücksetzt:
    
        Remove-CsExternalAccessPolicy -Identity global

## Siehe auch

#### Aufgaben

[Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  

#### Weitere Ressourcen

[Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

