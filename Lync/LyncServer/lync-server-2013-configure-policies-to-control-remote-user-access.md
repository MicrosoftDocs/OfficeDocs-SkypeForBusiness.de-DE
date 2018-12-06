---
title: 'Lync Server 2013: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer'
TOCTitle: Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398725(v=OCS.15)
ms:contentKeyID: 49294731
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Sie konfigurieren eine oder mehrere Richtlinien für den Zugriff externer Benutzer und steuern, ob Remotebenutzer mit internen Lync Server-Benutzern zusammenarbeiten können. Zum Steuern des Zugriffs durch Remotebenutzer können Sie Richtlinien auf globaler, Standort- und Benutzerebene konfigurieren. Standortrichtlinien setzen die globale Richtlinie außer Kraft, und Benutzerrichtlinien setzen Standort- und globale Richtlinien außer Kraft. Ausführliche Informationen zu den konfigurierbaren Richtlinientypen finden Sie unter [Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). Lync Server-Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien, und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.


> [!NOTE]
> Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer konfigurieren, wenn Sie den Zugriff durch Remotebenutzer für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien treten jedoch erst in Kraft, wenn der Zugriff durch Remotebenutzer für Ihre Organisation aktiviert wird. Ausführliche Informationen zum Aktivieren des Remotebenutzerzugriffs finden Sie unter <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</A>. Wenn Sie eine Benutzerrichtlinie zur Steuerung des Zugriffs durch Remotebenutzer angeben, gilt die Richtlinie zudem nur für Benutzer, die für Lync Server aktiviert und für die Verwendung der Richtlinie konfiguriert wurden. Ausführliche Informationen zum Angeben von Benutzern, die sich von Remotestandorten aus bei Lync Server anmelden können, finden Sie unter <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013</A>.



Führen Sie die folgenden Schritte aus, um die einzelnen Richtlinien für den externen Zugriff zu konfigurieren, die zur Steuerung des Remotebenutzerzugriffs verwendet werden sollen.


> [!NOTE]
> In diesem Verfahren wird lediglich beschrieben, wie Sie eine Richtlinie zum Aktivieren der Kommunikation mit Remotebenutzern konfigurieren. Sämtliche Richtlinien, die Sie für die Unterstützung des Remotebenutzerzugriffs konfigurieren, können jedoch ebenfalls zur Konfiguration des Zugriffs durch Partnerbenutzer und öffentliche Benutzer verwendet werden. Ausführliche Informationen zur Konfiguration von Richtlinien für die Unterstützung von Partnerbenutzern finden Sie unter <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013</A>. Ausführliche Informationen zur Konfiguration von Richtlinien für die Unterstützung von öffentlichen Benutzern finden Sie unter <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013</A>.



## So konfigurieren Sie eine Richtlinie für den externen Zugriff für die Unterstützung des Zugriffs durch Remotebenutzer

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff** .

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:
    
      - Um die globale Richtlinie für die Unterstützung des Zugriffs durch Remotebenutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen** .
    
      - Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie** . Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK** .
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie** . Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name** , der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableRemoteUsers** für eine Benutzerrichtlinie, welche die Kommunikation für Remotebenutzer ermöglicht).
    
      - Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen** .

5.  (Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren** , um den Zugriff durch Remotebenutzer für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Remotebenutzern aktivieren** , um den Zugriff durch Remotebenutzer für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit** .

Um den Zugriff durch Remotebenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Remotebenutzerzugriff in Ihrer Organisation aktivieren. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in der Bereitstellungs- bzw. Betriebsdokumentation.

Wenn es sich bei der Richtlinie um eine Benutzerrichtllinie handelt, dann müssen Sie diese auch auf Benutzer anwenden, die sich per Remotezugriff verbinden können sollen. Weitere Informationen finden Sie unter [Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer zu einem für Lync aktivierten Benutzer in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in der Bereitstellungs- bzw. Betriebsdokumentation.

