---
title: Angeben der Clientanwendungen, die zum Anmelden bei Lync Server 2013 verwendet werden können
TOCTitle: Angeben der Clientanwendungen, die zum Anmelden bei Lync Server 2013 verwendet werden können
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182591(v=OCS.15)
ms:contentKeyID: 49295489
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Angeben der Clientanwendungen, die zum Anmelden bei Lync Server 2013 verwendet werden können

 

_**Letztes Änderungsdatum des Themas:** 2012-12-11_

Lync Server 2013 ermöglicht Ihnen das Angeben der Clientversionen, die in Ihrer Umgebung unterstützt werden. Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden. Zur Nutzung aller Funktionen von Lync Server 2013 und zur Verbesserung des Benutzererlebnisses können Sie mit dem Clientversionsfilter festlegen, welche Clientversionen in Ihrer Lync Server 2013-Umgebung verwendet werden dürfen. Mit dem Clientversionsfilter können Sie außerdem die Kosten senken, die aufgrund der Unterstützung mehrerer Clientversionen anfallen.

Zusätzlich zum Erstellen einer globalen Richtlinie können Sie Clientversionsrichtlinien für einen bestimmten Dienst oder Standort erstellen oder Richtlinien auf Benutzerebene definieren, die einzelnen Benutzern zugewiesen werden können. Die Clientversionsrichtlinie auf Benutzerebene kann über die Gruppe **Benutzer** in der Lync Server-Systemsteuerung einzelnen Benutzern zugewiesen werden.


> [!NOTE]
> Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.




> [!IMPORTANT]
> Filter werden gemäß ihrer Rangfolge aufgelistet. Beispiel: Sie verfügen über einen Filter, der die Ausführung von Clientversion&nbsp;1.5 zulässt, gefolgt von einem Filter, der Clients mit früheren Versionen als Version&nbsp;2.0 blockiert. In diesem Fall hat der erste Filter Vorrang, und Clients mit Version&nbsp;1.5 können eine Verbindung herstellen.



## So bearbeiten Sie die standardmäßige Clientversionsrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**.
    

    > [!NOTE]
    > Die Registerkarte <STRONG>Clientversionsrichtlinie</STRONG> ist standardmäßig ausgewählt.



4.  Doppelklicken Sie auf der Seite **Clientversionsrichtlinie** auf die Richtlinie **Global** in der Liste.

5.  Führen Sie im Abschnitt **Clientversionsrichtlinie bearbeiten** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Neu**, um eine neue Clientversionsrichtlinie zu erstellen.
    
      - Klicken Sie auf einen der definierten Clienttypen in der Liste, und klicken Sie dann auf **Details einblenden**.
    

    > [!NOTE]
    > Sie können den Clienttyp mithilfe von Platzhalterzeichen angeben.



6.  Wählen Sie unter **Benutzer-Agent** einen Clienttyp aus.

7.  Führen Sie unter **Versionsnummer** die folgenden Aktionen aus:
    
      - Geben Sie in **Hauptversion** die Nummer ein, die der Hauptversion des Clients entspricht.
    
      - Geben Sie in **Nebenversion** die Nummer ein, die der Nebenversion des Clients entspricht.
    
      - Geben Sie in **Build** die Nummer ein, die der Haupt- und Nebenversion des Clients entspricht.
    
      - Geben Sie in **Update** die Nummer ein, die der aktualisierten Version des Clients entspricht.
    

    > [!NOTE]
    > Sie können die Clientversionsnummer mithilfe von Platzhalterzeichen angeben.



8.  Klicken Sie unter **Vergleichsvorgang** auf eine der folgenden Optionen, um den Vergleichsvorgang für die in den vorherigen Schritten angegebene Clientversion festzulegen:
    
      - **Gleich**
    
      - **Ungleich**
    
      - **Neuer als**
    
      - **Neuer als oder gleich**
    
      - **Älter als**
    
      - **Älter als oder gleich**

9.  Klicken Sie unter **Aktion** auf eine der folgenden Optionen, um die Aktion anzugeben, die bei Übereinstimmung mit dem angegebenen Kriterium ausgeführt werden soll:
    
      - Klicken Sie auf **Zulassen**, um die Anmeldung des Clients zu erlauben.
    
      - Klicken Sie auf **Zulassen und aktualisieren**, um dem Client die Anmeldung zu erlauben und Updates über Windows Server Update Service oder Microsoft Update abzurufen. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt wurde.
        

        > [!NOTE]
        > Wenn Sie diese Aktion auswählen, wird eine Benachrichtigung angezeigt, sobald sich Benutzer das nächste Mal bei Lync 2013 anmelden. Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft&nbsp;Update veröffentlicht wurden. Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.

    
      - Klicken Sie auf **Mit URL zulassen**, um die Anmeldung des Clients zu erlauben und den Benutzer in einer Meldung darauf hinzuweisen, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL später in diesem Verfahren an.
    
      - Um die Anmeldung des Clients zu verhindern, klicken Sie auf **Blockieren**.
    
      - Klicken Sie auf **Blockieren und aktualisieren**, um dem Client die Anmeldung zu verweigern und Updates über Windows Server Update Service oder Microsoft Update abzurufen. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt wurde.
    
      - Klicken Sie auf **Mit URL blockieren**, um die Anmeldung des Clients zu verweigern und den Benutzer in einer Meldung darauf hinzuweisen, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL später in diesem Verfahren an.

10. (Optional) Wenn Sie im vorherigen Schritt auf **Mit URL zulassen** oder **Mit URL blockieren** geklickt haben, geben Sie unter **URL** die URL für den Clientdownload ein.

11. Klicken Sie auf **OK** und dann auf **Commit ausführen**.

## Siehe auch

#### Weitere Ressourcen

[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

