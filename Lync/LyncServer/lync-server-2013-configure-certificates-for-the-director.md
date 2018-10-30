---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten für den Director'
TOCTitle: Konfigurieren von Zertifikaten für den Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398296(v=OCS.15)
ms:contentKeyID: 49293420
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Zertifikaten für den Director in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_


> [!IMPORTANT]
> Wenn Sie den Zertifikat-Assistenten ausführen, müssen Sie mit einem Konto angemeldet sein, das Mitglied einer Gruppe ist, die über die entsprechenden Berechtigungen für den von Ihnen verwendeten Zertifikatvorlagentyp verfügt. Für eine Lync Server 2013 -Zertifikatanforderung wird standardmäßig die Webserver-Zertifikatvorlage verwendet. Wenn Sie ein Konto verwenden, das Mitglied der RTCUniversalServerAdmins-Gruppe ist, kann mit dieser Vorlage nur ein Zertifikat angefordert werden, wenn dieser Gruppe die zum Verwenden dieser Vorlage erforderlichen Registrierungsberechtigungen erteilt wurden.



Für jeden Director wird ein Standardzertifikat, ein internes Webzertifikat und ein externes Webzertifikat benötigt. Ausführliche Informationen zu den Zertifikatanforderungen für Director-Server finden Sie unter [Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in der Planungsdokumentation.

Verwenden Sie das folgende Verfahren, um Director-Zertifikate zu konfigurieren. Wiederholen Sie das Verfahren für jeden Director. Die Schritte in diesem Verfahren beschreiben, wie Sie ein Zertifikat einer internen Stammzertifizierungsstelle konfigurieren, die in Ihrem Unternehmen eingesetzt wird. Zertifikatanforderungen werden in diesem Verfahren offline verarbeitet. Ausführliche Informationen zum Anfordern von Zertifikaten bei einer externen Zertifizierungsstelle erhalten Sie von Ihrem Support-Team.

## So konfigurieren Sie Zertifikate für den Director oder Director-Pool

1.  Klicken Sie im Lync Server-Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen** .

2.  Klicken Sie auf der Seite **Zertifikat-Assistent** auf **Anfordern** .

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **Weiter** .

4.  Akzeptieren Sie auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** , und klicken Sie dann auf **Weiter** .

5.  Klicken Sie auf der Seite **Zertifizierungsstelle auswählen** auf die interne Windows-Zertifizierungsstelle, die Sie verwenden möchten, und klicken Sie dann auf **Weiter** .

6.  Geben Sie auf der Seite **Zertifizierungsstellenkonto** alternative Anmeldeinformationen für den Fall an, dass das zur Anmeldung verwendete Konto keine ausreichenden Berechtigungen zum Anfordern des Zertifikats besitzt, und klicken Sie anschließend auf **Weiter** .

7.  Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter** .

8.  Geben Sie auf der Seite **Namens- und Sicherheitseinstellungen** einen Wert für **Anzeigename** ein, akzeptieren Sie die Schlüssellange von 2.048 Bit, und klicken Sie auf **Weiter** .

9.  Überprüfen Sie optional die Informationen auf der Seite **Organisationsinformationen** , und klicken Sie anschließend auf **Weiter** .

10. Überprüfen Sie optional die Informationen auf der Seite **Geografische Informationen** , und klicken Sie anschließend auf **Weiter** .

11. Klicken Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** auf **Weiter** .
    

    > [!NOTE]
    > Die Liste der alternativen Antragstellernamen sollte den Namen des Computers enthalten, auf dem Sie den Director installieren (falls nur ein Director vorhanden ist), andernfalls den Namen des Director-Pools und die Namen der einfachen URLs, die für die Organisation konfiguriert wurden.



12. Wählen Sie auf der Seite **SIP-Domäneneinstellung für alternative Antragstellernamen (SANs)** die Option **Konfigurierte SIP-Domänen** für alle Domänen aus, die der Director verarbeiten soll, und klicken Sie dann auf **Weiter** .

13. Geben Sie auf der Seite **Zusätzliche alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an, und klicken Sie auf **Weiter** .

14. Klicken Sie auf der Seite **Zusammenfassung der Zertifikatanforderung** auf **Weiter** .

15. Klicken Sie auf der Seite **Befehle ausführen** nach Abschluss der Befehlsausführung auf **Weiter** .

16. Klicken Sie auf der Seite **Status der Onlinezertifikatanforderung** auf **Fertig stellen** .

17. Klicken Sie auf der Seite **Zertifikatzuweisung** auf **Weiter** .
    

    > [!NOTE]
    > Wenn Sie das Zertifikat anzeigen möchten, doppelklicken Sie auf das Zertifikat in der Liste.



18. Klicken Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** auf **Weiter** .

19. Klicken Sie auf der Seite **Befehle ausführen** nach Abschluss der Befehlsausführung auf **Fertig stellen** .

20. Klicken Sie auf der Seite **Zertifizierungs-Assistent** auf **Schließen** .

