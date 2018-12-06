---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs'
TOCTitle: Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520946(v=OCS.15)
ms:contentKeyID: 49293103
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Über Verbindungen mit öffentlichen Instant Messaging-Diensten können Benutzer in Ihrer Organisation per Chatnachricht mit Benutzern von Instant Messaging-Diensten kommunizieren, die von öffentlichen Instant Messaging-Dienstanbietern bereitgestellt werden, z. B. vom Windows Live-Internetdienstnetzwerk, von Yahoo\! und von AOL. Sie konfigurieren eine oder mehrere Richtlinien für den Zugriff externer Benutzer und steuern, ob öffentliche Benutzer mit internen Lync Server-Benutzern zusammenarbeiten können. Bei den Verbindungen mit öffentlichen Instant Messaging-Diensten handelt es sich um ein Feature, das auf der Konfiguration der Bereitstellung und ihrer Benutzer beruht. Es hängt außerdem von der Bereitstellung des Diensts beim öffentlichen Instant Messaging-Anbieter ab. Informationen dazu, wie Sie Ihre Bereitstellung zur Verwendung der öffentlichen Anbieter bereitstellen, finden Sie im "Leitfaden zur Bereitstellung von Verbindungen mit öffentlichen Instant Messaging-Diensten für Microsoft Lync Server, Office Communications Server und Live Communications Server" unter <http://go.microsoft.com/fwlink/?linkid=269821>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
> <LI>
> <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>



Greifen Sie über den folgenden Link auf die Website für die Bereitstellung von Verbindungen mit öffentlichen Instant Messaging-Diensten für Microsoft Lync Server zu: <http://go.microsoft.com/fwlink/?linkid=212638>.

Zum Steuern des Zugriffs durch öffentliche Benutzer können Sie Richtlinien auf globaler Ebene und Standort- und Benutzerebene konfigurieren. Ausführliche Informationen zu den konfigurierbaren Richtlinientypen finden Sie in der Bereitstellungs- oder Planungsdokumentation unter [Konfigurieren der Unterstützung für den externen Benutzerzugriff in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md). Lync Server-Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien, und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.

Im Fall von Chatnachrichten-Einladungen hängt die Antwort von der Clientsoftware ab. Die Anforderung wird akzeptiert, sofern externe Absender nicht ausdrücklich durch eine vom Benutzer konfigurierte Regel (also Einstellungen in der **Zulassungs-** und **Blockierliste** des Benutzers) blockiert werden. Darüber hinaus können Chatnachrichten-Einladungen blockiert werden, wenn ein Benutzer festlegt, dass alle Chatnachrichten von Benutzern, die nicht in der **Zulassungsliste** enthalten sind, blockiert werden.


> [!NOTE]
> Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch öffentliche Benutzer konfigurieren, wenn Sie den Partnerverbund für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien treten jedoch erst dann in Kraft, wenn der Partnerverbund für Ihre Organisation aktiviert ist. Ausführliche Informationen zum Aktivieren des Partnerverbunds finden Sie in der Bereitstellungs- oder Betriebsdokumentation unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013</A>. Wenn Sie eine Benutzerrichtlinie zur Steuerung des Zugriffs durch öffentliche Benutzer angeben, gilt die Richtlinie zudem nur für Benutzer, die für Lync Server aktiviert und für die Verwendung der Richtlinie konfiguriert wurden. Ausführliche Informationen zum Angeben öffentlicher Benutzer, die sich bei Lync Server anmelden können, finden Sie in der Bereitstellungs- oder Betriebsdokumentation unter <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013</A>.



Gehen Sie folgendermaßen vor, um eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer eines oder mehrerer öffentlicher Instant Messaging-Anbieter zu konfigurieren.

## So konfigurieren Sie eine Richtlinie für den externen Zugriff für die Unterstützung des Zugriffs durch öffentliche Benutzer

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff** .

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:
    
      - Um die globale Richtlinie für die Unterstützung des Zugriffs durch öffentliche Benutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen** .
    
      - Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie** . Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK** .
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie** . Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name** , der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnablePublicUsers** für eine Benutzerrichtlinie, welche die Kommunikation für öffentliche Benutzer ermöglicht).
    
      - Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen** .

5.  (Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren** , um den Zugriff durch öffentliche Benutzer für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren** , um den Zugriff durch öffentliche Benutzer für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit** .

Um den Zugriff durch öffentliche Benutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerverbund in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

Handelt es sich um eine Benutzerrichtlinie, müssen Sie die Richtlinie auch auf öffentliche Benutzer anwenden, die mit öffentlichen Benutzern zusammenarbeiten sollen. Ausführliche Informationen finden Sie unter [Zuweisen von Richtlinien auf Benutzerebene](lync-server-2013-assigning-per-user-policies.md).

## Siehe auch

#### Aufgaben

[Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  

#### Weitere Ressourcen

[Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

