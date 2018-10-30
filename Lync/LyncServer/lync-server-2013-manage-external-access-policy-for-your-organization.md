---
title: 'Lync Server 2013: Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation'
TOCTitle: Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520995(v=OCS.15)
ms:contentKeyID: 49294041
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Nach der Bereitstellung eines oder mehrerer Edgeserver müssen Sie die spezifischen Typen des externen Benutzerzugriffs aktivieren, die für Ihre Organisation unterstützt werden sollen.

In der Standardeinstellung sind keine Richtlinien für den Zugriff durch externe Benutzer (einschließlich Remotebenutzerzugriff und Partnerbenutzerzugriff) konfiguriert. Dies gilt auch, wenn Sie die Unterstützung für externe Benutzer in Ihrer Organisation bereits aktiviert haben. Um den Zugriff durch externe Benutzer zu kontrollieren, müssen Sie eine oder mehrere Richtlinien konfigurieren und die Art des Benutzerzugriffs angeben, der durch die jeweilige Richtlinie ermöglicht wird. Sie können die nachstehend angegebenen Richtlinienbereiche erstellen und konfigurieren. Die "Globale Richtlinie" wird standardmäßig erstellt. Sie kann nicht gelöscht werden.

  - **Globale Richtlinie :** Diese Richtlinie wird erstellt, wenn Sie Ihre Edge-Server bereitstellen. Optionen für den Zugriff durch externe Benutzer sind in der globalen Richtlinie zunächst nicht aktiviert. Um den Zugriff durch externe Benutzer auf globaler Ebene zu unterstützen, konfigurieren Sie die entsprechende Richtlinie, sodass eine oder mehrere Optionen für den Zugriff durch externe Benutzer unterstützt werden. Die globale Richtlinie wird für alle Benutzer in der Organisation verwendet. Sie kann jedoch durch Standortrichtlinien und Benutzerrichtlinien überschrieben werden. Wenn Sie die globale Richtlinie löschen, wird diese nicht entfernt, sondern auf die Standardeinstellung zurückgesetzt.

  - **Standortrichtlinie :** Sie können eine oder mehrere Standortrichtlinien erstellen und konfigurieren, um den Zugriff für externe Benutzer auf bestimmte Standorte zu beschränken. Die Konfiguration der Standortrichtlinie überschreibt die globale Richtlinie. Dies gilt jedoch nur für den in der entsprechenden Richtlinie angegebenen Standort. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, können Sie eine Standortrichtlinie festlegen, die den Remotebenutzerzugriff für einen bestimmten Standort deaktiviert. Standardmäßig wird eine Standortrichtlinie auf alle Benutzer des jeweiligen Standorts angewendet. Sie können jedoch einem Benutzer eine Benutzerrichtlinie zuweisen, um die Standortrichtlinieneinstellung außer Kraft zu setzen.

  - **Benutzerrichtlinie :** Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um den Remotebenutzerzugriff auf bestimmte Benutzer zu beschränken. Die Konfiguration der Benutzerrichtlinie überschreibt die globale Richtlinie und die Standortrichtlinie. Dies gilt jedoch nur für die von der entsprechenden Richtlinie betroffenen Benutzer. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und in der Standardrichtlinie aktivieren, können Sie eine Benutzerrichtlinie festlegen, die den Remotebenutzerzugriff deaktiviert, und diese Richtlinie bestimmten Benutzern zuweisen. Benutzerrichtlinien werden erst mit der Zuweisung zu bestimmten Benutzern wirksam.


> [!IMPORTANT]
> Lync Server-Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien, und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.



Diese Optionen umfassen folgende Arten des externen Zugriffs:

  - **Kommunikation mit Partnerbenutzern aktivieren** : Aktivieren Sie diese Option, wenn Sie den Zugriff von Benutzern auf Partnerdomänen unterstützen möchten. Diese Einstellung legt die Möglichkeit von Benutzern fest, mit Benutzern in anderen SIP-Partnerdomänen sowie mit Hostinganbietern wie Microsoft Office 365 zu kommunizieren. Wenn Sie diese Einstellung auswählen, können Sie auch die Option zum Aktivieren der Kommunikation mit XMPP-Verbunddomänen auswählen.
    
    Sie können die Option **Kommunikation mit XMPP-Verbundpartnern aktivieren** auswählen, wenn Sie zuvor die Option **Kommunikation mit Partnerbenutzern aktivieren** ausgewählt haben. XMPP-Verbünde sind Verbünde mit Organisationen, die das Extensible Messaging and Presence Protocol (XMPP) verwenden.
    

    > [!NOTE]
    > Wenn Sie XMPP-Verbünde aktivieren, müssen Sie auch die Bereitstellung des <STRONG>XMPP-Verbunds</STRONG> im Edgepools-Konfigurationsabschnitt von Topologie-Generator auswählen. Durch das Konfigurieren von XMPP-Verbünden wird ein XMPP-Proxy in der Edgeserver sowie ein XMPP-Gateway in der Front-End-Server bereitgestellt.



  - **Kommunikation mit Remotebenutzern aktivieren** : Aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation in der Lage sein sollen, die sich außerhalb der Firewall befinden, z. B. Telearbeiter und Benutzer auf Geschäftsreise), sich über das Internet mit Lync Server verbinden zu können.

  - **Kommunikation mit öffentlichen Benutzern aktivieren**    Aktivieren Sie diese Option, wenn sich interne Benutzer mit öffentlichen Kontakten der Anbieter von Instant-Messaging-Diensten wie Windows Live, Yahoo\! oder AOL verbinden können sollen.
    

    > [!IMPORTANT]
    > <UL>
    > <LI>
    > <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
    > <LI>
    > <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
    > <LI>
    > <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>




> [!NOTE]
> Neben dem Aktivieren der Unterstützung für den externen Benutzerzugriff müssen Sie auch Richtlinien konfigurieren, um die Verwendung des externen Benutzerzugriffs in Ihrer Organisation zu steuern, bevor den Benutzern ein beliebiger Typ des externen Benutzerzugriffs zur Verfügung steht. Ausführliche Informationen zur Erstellung, Konfiguration und Anwendung von Richtlinien für den externen Benutzerzugriff finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013</A>.



**So zeigen Sie Richtlinien für den externen Zugriff mit den Windows PowerShell-Cmdlets an**

  - Externe Zugriffsrichtlinien können mit der Lync Server-Verwaltungsshell und mit dem Cmdlet **Get-CsExternalAccessPolicy** angezeigt werden. Sie können dieses Cmdlet in der Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Um Informationen über alle Richtlinien für den externen Zugriff anzuzeigen, geben Sie den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie die EINGABETASTE:
    
        Get-CsExternalAccessPolicy
    
    Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

## In diesem Abschnitt

  - [Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Zurücksetzen oder Löschen von Richtlinien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

