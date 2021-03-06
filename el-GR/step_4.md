## Αποθήκευση των πληροφοριών

Αυτήν τη στιγμή, η εφαρμογή σου αποθηκεύει πληροφορίες μόνο εφόσον αυτή εκτελείται. Θα ήταν πολύ πιο χρήσιμο να θυμάται τον χρόνο άσκησης ακόμα και όταν την κλείσεις ή την επανεκκινήσεις, σωστά; Για να το κάνεις αυτό, θα αποθηκεύσεις τις πληροφορίες σε ένα αρχείο στο τηλέφωνο ή το tablet σου και κάθε φορά που θα ξεκινά η εφαρμογή θα διαβάζει από αυτό το αρχείο.

+ Στην προβολή Designer, πρόσθεσε ένα **File** στοιχείο στην εφαρμογή σου. Θα το βρεις στην επιλογή **Storage**. Αυτό είναι ένα αόρατο στοιχείο, έτσι δεν θα το δεις στην οθόνη.

![](images/s5StorageFile.png)

+ Τώρα πήγαινε στην προβολή Blocks και κάνε κλικ στο File1 για να πάρεις το μπλοκ `call File1.AppendToFile`. Πρόσθεσέ το στον κώδικα σου μετά από το μπλοκ `set Label.Text to`.

![](images/s5AppendToFile.png)


--- collapse ---
---
title: Τι κάνει το νέο μπλοκ;
---

Αυτό το μπλοκ παίρνει δύο **παραμέτρους**. Μια παράμετρος είναι μια πληροφορία που δίνεται στο μπλοκ. Συνήθως, το μπλοκ θα κάνει κάτι με αυτή την πληροφορία.

Η πρώτη παράμετρος, `text`, είναι το κείμενο που θέλεις να αποθηκεύσεις σε ένα αρχείο. Η δεύτερη, `fileName` είναι το όνομα του αρχείου που θέλεις να χρησιμοποιήσεις για την αποθήκευση.

Ο κώδικας θα πάρει το κείμενο που του δίνεις και θα το προσθέσει στο τέλος του κειμένου στο αρχείο. Το πραγματικά βολικό είναι ότι αν το αρχείο δεν υπάρχει ακόμα, την πρώτη φορά το μπλοκ θα το δημιουργήσει.

--- /collapse ---

+ Για την παράμετρο `fileName`, κούμπωσε ένα μπλοκ `""` από το Text και πληκτρολόγησε `ExerciseTracker.txt`.

+ Για την `text` παράμετρο, κούμπωσε ένα `join` μπλοκ, ένα `get mins` μπλοκ, και ένα ακόμη κενό `«»` μπλοκ κειμένου. Πληκτρολόγησε `\n` στο κενό μπλοκ κειμένου (βεβαιώσου ότι χρησιμοποιείς μια αντίστροφη κάθετο `\` 'και **όχι** μια εμπρόσθια κάθετο `/`).

![](images/s5JoinMinsNewline.png)

--- collapse ---
---
title: Τι έγραψα ακριβώς;
---

Το σύμβολο `\n` είναι ένας ειδικός συνδυασμός χαρακτήρων που χρησιμοποιούνται όταν θέλεις να μεταβείς σε μια νέα γραμμή σε ένα κείμενο.

Ο κώδικάς σου λαμβάνει τον αριθμό των λεπτών που πληκτρολογήθηκε από τον χρήστη και προσθέτει μια νέα γραμμή στο τέλος, πριν την αποθηκεύσει στο αρχείο.

Αυτό σημαίνει ότι κάθε φορά που ο χρήστης εισάγει ένα αριθμό λεπτών, θα αποθηκευτεί σε μια ξεχωριστή γραμμή στο αρχείο κειμένου που έχεις ονομάσει `ExerciseTracker.txt`.

--- /collapse ---

Τώρα που έχεις αποθηκεύσει δεδομένα στο αρχείο, πρέπει να διαβάσεις αυτά τα δεδομένα κάθε φορά που φορτώνεται η εφαρμογή!

+ Πάρε ένα `when Screen1.initialise` μπλοκ, και βάλε μέσα σ' αυτό ένα `call File1.readFrom` μπλοκ κλήσης, κουμπώνοντας ένα μπλοκ κειμένου στο οποίο θα πληκτρολογήσεις όπως πριν `ExerciseTracker.txt`.

![](images/s5ScreenInit.png)

Αυτή η κλήση είναι **ασύγχρονη**, πράγμα που σημαίνει ότι θα πάει και θα διαβάσει το αρχείο και μετά θα ειδοποιήσει πως ολοκληρώθηκε.

+ Από την επιλογή File1 στ' αριστερά, βγάλε ένα `when File1.GotText` μπλοκ.

Η μεταβλητή `text` περιέχει όλο το κείμενο από το αρχείο. Θα το χρησιμοποιήσεις για να γεμίσεις τη μεταβλητή **list** που δημιούργησες για τη συλλογή των λεπτών. Αλλά πρώτα, πρέπει να το διασπάσεις για να διαχωρίσεις κάθε γραμμή.

+ Πρόσθεσε τα παρακάτω μπλοκ μέσα στο `GotText`:

![](images/s5GotTextSplit.png)

--- collapse ---
---
title: Πώς λειτουργεί η διάσπαση;
---

Το μπλοκ `split` παίρνει ένα κομμάτι κειμένου και το χωρίζει σε πολλά ξεχωριστά κομμάτια.

Φαντάσου ότι έχεις ένα μεγάλο κείμενο και αποτελείται από μια δέσμη τεμαχίων που ενώνονται με κουκκίδες ανάμεσά τους. Η χρήση του μπλοκ `split` θα σου επιτρέψει να σπάσεις αυτό το κείμενο σε ξεχωριστά κομμάτια κειμένου και να αφαιρέσεις τις τελείες.

Αυτό που βάζεις στο `at` αποφασίζει για το πώς γίνεται η διάσπαση του κειμένου.

Αναζητά το κείμενο για την τιμή στο μπλοκ `at` και κάθε φορά που το βρίσκει, «κόβει» ένα ακόμη κομμάτι του κειμένου. Το κείμενο που αντιστοιχεί στην τιμή του `at` διαγράφεται στη συνέχεια.

Αυτό που παίρνεις πίσω είναι μια λίστα που περιέχει μια δέσμη ξεχωριστών κομματιών κειμένου!

--- /collapse ---

Τώρα θα συνοψίσεις όλα τα λεπτά που μόλις φορτώσες από το αρχείο και θα εμφανίσεις το σύνολο.

+ Κάτω από το μπλοκ `set global minutesList`, πρόσθεσε κώδικα για να ορίσεις την καθολική μεταβλητή `totalTime` ως `0`:

![](images.s5SetTotalZero.png)

+ Στα μπλοκ ελέγχου Controls, βρες το μπλοκ `for each item in list` και κούμπωσε σ'αυτό ένα `get global minutesList`.

![](images/s5ForEach.png)

+ Μέσα σε αυτό, πρόσθεσε ένα `set global totalTime to` μπλοκ, και στη συνέχεια ένα `+` μπλοκ με `get global totalTime` στα αριστερά του. Θυμήσου, το έκανες αυτό και πριν για να προσθέσεις κάτι στο σύνολο. Η μόνη διαφορά αυτή τη φορά είναι ότι η μεταβλητή που βάζεις στα δεξιά του `+` είναι: το τρέχον `item` (στοιχείο) της λίστας.

![](images.s5ForEachItemIterate.png)

+ Τέλος, πρόσθεσε το `set Label.Text to` και το `get global totalTime` μπλοκ όπως πριν.

+ Να πώς θα πρέπει να μοιάζει τώρα το μπλοκ `GotText`. Δοκίμασε την εφαρμογή σου για να βεβαιωθείς ότι όλα λειτουργούν!

![](images/s5GotTextAll.png)

