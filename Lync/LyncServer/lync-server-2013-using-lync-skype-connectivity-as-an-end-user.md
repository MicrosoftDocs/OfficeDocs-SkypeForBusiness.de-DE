---
title: 'Lync Server 2013: Verwenden von Lync-Skype-Konnektivität als Endbenutzer'
TOCTitle: Verwenden von Lync-Skype-Konnektivität als Endbenutzer
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn440175(v=OCS.15)
ms:contentKeyID: 59373615
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von Lync-Skype-Konnektivität als Endbenutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-27_

Mit der Lync-Skype-Konnektivität können Skype-Benutzer und Lync-Benutzer sich wechselseitig als Kontakte hinzufügen, Chatnachrichten austauschen sowie Audio- und Videoanrufe führen. Wenn ein Skype-Benutzer einen Lync-Benutzer hinzufügt, erstellt der Skype-Benutzer einen Kontakt in Skype, der den SIP-URI (Session Initiation-Protokoll Uniform Resource Identifier) des Lync-Benutzers enthält. Umgekehrt erstellt ein Lync-Benutzer, wenn der Lync-Benutzer einen Skype-Kontakt hinzufügt, einen Kontakt in Lync, der das Microsoft-Konto (Microsoft Account, MSA) des Skype-Benutzers, nicht den Skype-Benutzernamen enthält.

**Was ist ein MSA?** Skype-Benutzer müssen sich bei Skype mit einem Microsoft-Konto (bisher als Windows Live ID bezeichnet) anmelden, damit sie mit Lync-Kontakten kommunizieren können. Ein Microsoft-Konto besteht aus der Kombination einer E-Mail-Adresse und eines Kennworts, die Sie auch dazu verwenden können, sich bei Diensten wie Microsoft OneDrive-Speichertechnologie, Windows Phone, Microsoft Xbox LIVE (Onlinedienst für Spiele) sowie bei einem Microsoft Outlook-Client für Messaging und Zusammenarbeit (und, früher, dem webbasierten E-Mail-Dienst Microsoft Hotmail oder Windows Live Messenger) anzumelden. Wenn Sie sich bei diesen oder anderen Diensten bereits mit einer E-Mail-Adresse und einem Kennwort anmelden, verfügen Sie schon über ein Microsoft-Konto. Ausführliche Informationen zum Erstellen eines Microsoft-Kontos finden Sie auf der Anmeldeseite für ein Microsoft-Konto unter [http://go.microsoft.com/fwlink/p/?LinkId=306061](http://go.microsoft.com/fwlink/p/?linkid=306061). Sie können Ihr vorhandenes Skype-Konto mit Ihrem Microsoft-Konto zusammenführen, um sich per einmaliger Anmeldung (Single Sign-on, SSO) bei einer Vielzahl von Anwendungen und Diensten anzumelden. Sobald das Konto zusammengeführt ist, kann ein Skype-Benutzer Kontaktanfragen an Lync-Benutzer senden.


> [!IMPORTANT]
> Damit Lync- und Skype-Benutzer uneingeschränkt miteinander kommunizieren können, müssen die folgenden Voraussetzungen erfüllt sein: 
> <UL>
> <LI>
> <P>Skype-Benutzer müssen bei ihren Skype-Clients mit dem entsprechenden Microsoft-Konto (Microsoft Account, MSA) angemeldet sein.</P>
> <LI>
> <P>Lync-Benutzern muss durch den Lync-Administrator die Nutzung öffentlicher Instant Messaging-Dienste gestattet sein.</P>
> <LI>
> <P>Wenn ein Skype-Benutzer einen Lync-Kontakt hinzufügt, muss das Wort <STRONG>Lync</STRONG> unter dem Namen des Kontakts angezeigt werden. Dadurch ist gekennzeichnet, dass ein Lync-URI gefunden wurde.</P>
> <LI>
> <P>Wenn ein Skype-Benutzer einen Lync-Kontakt hinzufügt und für die zugehörige Lync-Domäne keine Suchergebnisse zurückgegeben werden, ist der PIC-Vermittlungsprozess möglicherweise noch nicht abgeschlossen, oder die Domäne wurde noch nicht eingerichtet.</P>
> <LI>
> <P>Je nach Datenschutzeinstellungen der Lync- und Skype-Benutzer funktionieren Chat, Video und Anwesenheit möglicherweise erst, nachdem die neuen Kontakte von jedem Benutzer akzeptiert wurden.</P></LI></UL>



**So fügen Sie eine Skype-Kontakt in Lync 2013 hinzu**

1.  Klicken Sie in Lync auf **Kontakt hinzufügen, Externen Kontakt hinzufügen**.

2.  Wählen Sie in der Liste der verfügbaren Kontaktanbieter den Eintrag **Skype** aus.
    
    ![Lync-Client, der zeigt, wie ein Skype-Kontakt hinzugefügt wird](images/Dn440175.ac4e2f21-c1d9-47d8-b99e-d49fe4eb36d7(OCS.15).jpg "Lync-Client, der zeigt, wie ein Skype-Kontakt hinzugefügt wird")

3.  Geben Sie in das Feld **Chatadresse** das Microsoft-Konto des Skype-Benutzers ein.

4.  Wählen Sie im Dropdownfeld **Zu Kontaktgruppe hinzufügen** die Kontaktgruppe aus, zu der der Benutzer hinzugefügt werden soll.

5.  Wählen Sie im Dropdownfeld **Private Beziehung festlegen** die gewünschte Kontakteinstellung aus, und klicken Sie dann auf **OK**.

6.  Der Benutzer wird nun als Kontakt in Lync angezeigt. Wählen Sie den Benutzer aus, klicken Sie mit der rechten Maustaste auf den Benutzernamen und klicken Sie auf **Visitenkarte anzeigen**, damit die Benutzereigenschaften angezeigt werden. Wie in der nächsten Abbildung gezeigt, können Sie auch auf **Anruf** und dann auf **Lync-Anruf** klicken, um einen Audio- oder Videoanruf mit dem neu hinzugefügten Skype-Benutzer zu beginnen.
    
    ![Lync-Client, der einen Lync-Anruf zu einem Kontakt startet](images/Dn440175.cd7cb21a-87f7-4bfa-b30c-980d4098d226(OCS.15).jpg "Lync-Client, der einen Lync-Anruf zu einem Kontakt startet")

Weitere Informationen zu der Unterstützung für Kontakte finden Sie unter [Hinzufügen eines Kontakts in Lync](http://office.microsoft.com/de-de/office365-lync-online-help/add-a-contact-in-lync-ha102828922.aspx) und [Hinzufügen eines externen Kontakts in Lync](http://office.microsoft.com/de-de/office365-lync-online-help/add-an-external-contact-in-lync-ha104038998.aspx?ctt=5%26origin=ha102828922)

Wenn das Microsoft-Konto eines Skype-Benutzers einen benutzerdefinierten Domänennamen enthält, beispielsweise <strong>bob@contoso.com</strong>, kann ein Lync-Benutzer dieses Microsoft-Konto auf zwei Arten in Lync hinzufügen:

1.  über das Symbol **Kontakt hinzufügen** oder

2.  über das Feld **Suchen Sie nach Personen oder Chatrooms, oder wählen Sie eine Rufnummer**

In beiden Fällen muss der Lync-Benutzer die E-Mail-Adresse des Skype-Benutzers im folgenden Format eingeben: <strong>Benutzer(Domänenname)@msn.com</strong>.


> [!IMPORTANT]
> Dieser Schritt ist nicht für Microsoft-Konten erforderlich, in denen einer der folgenden Domänennamen verwendet wird: <STRONG>@live.com, @hotmail.com oder @outlook.com</STRONG>. Weitere Informationen zu unterstützten benutzerdefinierten Domänennamen finden Sie unter <A href="http://support.microsoft.com/kb/897567">Unterstützte öffentliche Chatdomänen</A>.



**So fügen Sie einen Skype-Kontakt in Lync hinzu, wenn ein benutzerdefinierter Domänenname verwendet wird**

1.  Klicken Sie in Lync auf **Kontakt hinzufügen, Externen Kontakt hinzufügen**.

2.  Wählen Sie in der Liste der verfügbaren Kontaktanbieter den Eintrag **Skype** aus.
    
    ![Lync-Client, der zeigt, wie ein Skype-Kontakt hinzugefügt wird](images/Dn440175.ac4e2f21-c1d9-47d8-b99e-d49fe4eb36d7(OCS.15).jpg "Lync-Client, der zeigt, wie ein Skype-Kontakt hinzugefügt wird")

3.  Geben Sie in das Feld **Chatadresse** das Microsoft-Konto des Skype-Benutzers im Format <strong>Benutzer(Domänenname)@msn.com</strong> ein. Für den Benutzer <strong>bob@contoso.com</strong> würde der Eintrag also <strong>bob(contoso.com)@msn.com</strong> lauten (siehe folgende Abbildung).
    
    ![Lync-Client – neue Kontakte (Einstellungen)](images/Dn440175.422e69b5-2c0c-4260-858f-f10309af772f(OCS.15).jpg "Lync-Client – neue Kontakte (Einstellungen)")

4.  Wählen Sie im Dropdown-Listenfeld **Zu Kontaktgruppe hinzufügen** die Kontaktgruppe aus, zu der der Benutzer hinzugefügt werden soll.

5.  Wählen Sie im Dropdown-Listenfeld **Private Beziehung festlegen** die geeignete Kontakteinstellung aus, und klicken Sie dann auf **OK**.

6.  Ein Lync-Benutzer kann auch das Feld **Suchen Sie nach Personen oder Chatrooms, oder wählen Sie eine Rufnummer** in Lync verwenden und eine Adresse hinzufügen, die das Format <strong>Benutzer(Domänenname)@msn.com</strong> hat. Für das Microsoft-Konto <strong>bob@contoso.com</strong> würde der Eintrag also <strong>bob(contoso.com)@msn.com</strong> lauten.
    
    ![Suche nach einem Kontakt in Lync-Client](images/Dn440175.69787db8-f9b9-49e5-b197-b90b10393301(OCS.15).jpg "Suche nach einem Kontakt in Lync-Client")

7.  Führen Sie die Schritte 4 und 5 aus dieser Schrittfolge aus, um den Kontakt zu einer Kontaktgruppe hinzuzufügen und die gewünschte Datenschutzeinstellung auszuwählen.

**So fügen Sie einen Lync-Kontakt in Skype hinzu**

1.  Melden Sie sich bei Skype an. Der Skype-Benutzer muss bei seinem Skype-Client mit einem Microsoft-Konto angemeldet sein.
    
    ![Anmelden bei Skype-Client (Seite)](images/Dn440175.b4fd7c5a-be35-4205-80c7-872863b7a91d(OCS.15).jpg "Anmelden bei Skype-Client (Seite)")

2.  Wählen Sie das Symbol für das Hinzufügen eines Kontakts aus.

3.  Geben Sie den SIP-URI des Lync-Benutzers ein. Beispiel: <strong>bob@contoso.com</strong>.

4.  Wenn Skype den passenden Kontakt in den Suchergebnissen findet, suchen Sie nach dem Wort **Lync** unter dem Namen des Lync-Benutzers. Hierdurch ist gekennzeichnet, dass der SIP-URI des Lync-Clients erfolgreich von Skype gefunden wurde. Klicken Sie auf den Namen.
    
    ![Skype-Client mit Lync-Kontakt](images/Dn440175.4e690a72-1a54-4442-89cf-0fb45ac5f56a(OCS.15).jpg "Skype-Client mit Lync-Kontakt")

5.  Klicken Sie in der oberen rechten Ecke des Fensters auf **Zu Kontakten hinzufügen**.

6.  Der neue Kontakt ist nun zu Ihrer Kontaktliste hinzugefügt. Solange der Kontakt Ihre Anfrage aber nicht akzeptiert hat, sehen Sie nicht dessen Statussymbol, sondern ein Fragezeichen. Sobald Ihr neuer Kontakt Ihre Anfrage akzeptiert hat, können Sie sehen, ob der Kontakt online ist, Chatunterhaltungen beginnen sowie Audio- und Videoanrufe führen.
    
    ![Skype-Client – Chatunterhaltung mit einem Lync-Kontakt](images/Dn440175.86ca6f81-4db9-45ba-8511-1f7541aaf066(OCS.15).jpg "Skype-Client – Chatunterhaltung mit einem Lync-Kontakt")
    

    > [!IMPORTANT]
    > Der Lync Server-Administrator muss die Richtlinieneinstellungen des Lync-Benutzers so konfigurieren, dass eingehende Anforderungen zugelassen werden. Ist dies nicht der Fall, empfängt der Lync-Benutzer keine Kontaktanforderungen vom Skype-Benutzer. Je nach Konfiguration der Richtlinieneinstellungen des Lync-Benutzers wird die Anforderung, den Skype-Benutzer hinzuzufügen, im Lync-Client auf dessen Registerkarte <STRONG>Neu</STRONG> angezeigt. Damit der Lync-Benutzer mit dem Skype-Benutzer kommunizieren kann, muss der Lync-Benutzer den Skype-Benutzer entweder zur Liste <STRONG>Favoriten</STRONG> oder zu einer Kontaktliste hinzufügen. In der nächsten Abbildung ist die Position gezeigt, die die Registerkarte <STRONG>Neu</STRONG> im Lync-Client hat.

    
    ![Lync-Client – neue Kontakte (Seite)](images/Dn440175.b1cf8570-1401-47d9-ab14-b04f0d7e8a7a(OCS.15).jpg "Lync-Client – neue Kontakte (Seite)")

Ein Lync-Benutzer muss Lync-Benachrichtigungen konfigurieren, damit sichergestellt ist, dass Anforderungen, die von einem Skype-Benutzer gesendet wurden, angezeigt werden und für ihn erkennbar sind. Wenn Sie Lync-Benachrichtigungen konfigurieren möchten, führen Sie die folgenden Schritte aus.

**So konfigurieren Sie Lync-Benachrichtigungen**

1.  Klicken Sie im Lync-Client auf das Symbol **Optionen**.

2.  Wählen Sie **Benachrichtigungen** aus.

3.  Aktivieren Sie unter **Allgemeine Benachrichtigungen** das Kontrollkästchen **Mitteilung an mich, wenn ich zur Kontaktliste einer anderen Person hinzugefügt werde**.

4.  Aktivieren Sie unter **Kontakte, die kein Lync verwenden** die Option **Einladungen zulassen, aber jegliche andere Kommunikation blockieren**.

5.  Klicken Sie auf **OK**, um das Fenster **Optionen** zu schließen.

![Lync-Clientoptionen (Dialogfeld), Warnungen (Seite)](images/Dn440175.b36ed67f-f394-4f66-b60a-b74793001bfc(OCS.15).jpg "Lync-Clientoptionen (Dialogfeld), Warnungen (Seite)")

