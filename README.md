<body>
<h3>vvv  SCROLL DOWN FOR ENGLISH VERSION  vvv</h3>
<img src="ProjectImages\ReadmeFirstImage.PNG" alt="InventoryViewport" width="800" >


<h1>### Projeto inventário ###</h1>
<h3>Esse projeto é parte de um estudo seguindo o curso 'Unreal Engine 5 UI Design: Advance inventory system with UE5', do instrutor Mr. Navid, Unreal Magic, na Udemy.</h3>
<p>Tanto o curso quanto meu projeto são inspirados em Legends Of Zelda, eu experimentei trazer assets diferentes, porém a similaridade é evidente.</p>

<p>Esse projeto não receberá mais atualizações, a finalidade dele é ser uma apresentação do meu conhecimento em manipular Arrays e lidar com Interface, BlueprintComponents, UserInterface, incluindo drag and drop além de um menu de ação para itens em abas diferentes do inventário.</p>

<h1>### Etapas ###</h1>
<p>Com o objetivo de o projeto ser usado em ideias futuras, segui as dicas do instrutor do curso de manter tudo modular, tanto os arquivos e suas pastas, quanto os códigos, usando funções e componentes adicionados ao meu player ("BP_ThirdPersonCharacter"), evitando assim usos recorrentes do node "CastTo", o que otimiza a performance do jogo e a experiencia do jogador.</p>

<h2>BPC_Inventory</h2>
<p>Primeiramente criei as inicializações da BlueprintComponent adicionando MappingContext do PlayerController para o InputMappingContext do inventário.</p>
<p>Ao iniciar a WidgetBlueprint do inventário, usei CastToBP_ThirdPersonCharacter para salvar a variavel do Player, usei BindEventToComponentBeginOverlap na CapsuleComponent para o sistema de coletar o que chamei de dinheiro.</p>
<img src="ProjectImages\CurrencyAssets.PNG" alt="CurrencyAssets" width="400" >
<img src="ProjectImages\CurrencyAdd.PNG" alt="CurrencyAdd" width="400" >
<p>Inclui a barra de vida e a contagem do dinheiro na Viewport do jogo, e configurei o tamanho dos inventários.</p>

<h3>AddToInventory</h3>
<p>Usei EnhancedInputAction IA_Interact configurado na tecla 'E' para chamar a função Trace Item, e AddToInventory</p>
<p>A função TraceItemToPickUp verifica a colisão de atores e a implementação da interface BPI_Item dentro de um raio de 90 unidades a 50 unidades à frente do Player e retorna o sucesso.</p>
<img src="ProjectImages\BPCAddToInventoryCall.PNG" alt="BPCAddToInventoryCall" width="400" >

<p>Com isso a função AddToInventory pode ser executada</p>
<p>Essa função será executada de acordo com o tipo do item, definido por Enumerators.</p>
<p>Fazendo a conferencia do inventário em um loop, correlacionando o nome do item vindo do Trace Item, seu StackSize e adicionando corretamente em seu Array.</p>
<p>Isso faz com que o item seja exibido na UserInterface quando a tecla 'I' é pressionada chamando a função UpdateInventoryUI, e abrindo o inventário na tela.</p>
<img src="ProjectImages\BPCAddToInventory.PNG" alt="BPCAddToInventory" width="400" >
<img src="ProjectImages\UpdateInventoryUI.PNG" alt="UpdateInventoryUI" width="400" >
<img src="ProjectImages\ReadmeFirstImage.PNG" alt="InventoryFirstImage" width="400" >
<img src="ProjectImages\FoodTab.PNG" alt="FoodTab" width="400" >
<img src="ProjectImages\QuestItemsTab.PNG" alt="QuestItemsTab" width="400" >
<img src="ProjectImages\ShieldsTab.PNG" alt="ShieldsTab" width="400" >
<img src="ProjectImages\SwordsTab.PNG" alt="SwordsTab" width="400" >

<h2>Drag and Drop</h2>
<p>Para o Drag and Drop eu usei a função da Unreal OnPreviewMouseButtonDown, para detectar o segurar do botão direito do mouse (essa mesma função está sendo usada para o menu de ação do item dentro do slot com o botão esquerdo do mouse).</p>
<img src="ProjectImages\DragDropDetect.PNG" alt="DragDropDetect" width="400" >
<p>Com DragDetected, o item pode ser retirado de seu Array e suas variáveis, em Structure, e seu Index atual podem ser passados para a DragAndDropBlueprint.</p>
<img src="ProjectImages\DragDetect.PNG" alt="DragDetect" width="400" >
<p>Ao Drop, primeiro confiro se o mesmo item esta naquele slot, isso faz o item voltar para seu antigo index.</p>
<p>Outro caso é o slot vazio, ou com outro item, sendo possivel assim que o item dropado seja criado naquele index, ou troque de posição com o item na posição atual.</p>
<img src="ProjectImages\DropDetect0.PNG" alt="DropDetect" width="400" >
<p>Caso o item seja dropado em qualquer lugar que não seja o slot, criei uma redundância para que ele volte para seu index original.</p>
<img src="ProjectImages\DropInNoSlot.PNG" alt="DropInNoSlot" width="400" >

<h2>Action Menu</h2>
<p>O botão de ação é o primeiro botão do menu, que é criado ao clicar com o botão esquedo do mouse no item do slot.</p>
<p>Usado para Equipar itens na mão esqueda e direita do Player.</p>
<p>Para a aba de alimentos, ao clique do botão de ação, a função UseEatables é chamada para modificar a vida atual do Player.</p>
<img src="ProjectImages\ActionMenuUseEquip.PNG" alt="ActionMenuUseEquip" width="400" >
<img src="ProjectImages\ActionMenuEatables.PNG" alt="ActionMenuEatables" width="400" >
<img src="ProjectImages\ActionMenu.PNG" alt="DropInNoSlot" width="400" >

<p>O botão de cancel simplesmente fecha o menu, porem há redundâncias nesse sistema para se fechar ao tirar o mouse da area do botão.</p>
<p>O botão Drop faz conferencias diferentes para o tipo do item selecionado, usado para desequipar itens ao drop.</p>
<img src="ProjectImages\ActionMenuDrop.PNG" alt="ActionMenuDrop" width="400" >

<h1>### Conclusão ###</h1>
<h3>Um outro projeto usando a estrutura aprendida e documentada aqui esta em andamento, por isso em algumas imagens pode ser visto a logica ja sendo aplicada, introduzindo uma mecanica de quest.</h3>
<p>Agradeço muito ao instrutor do curso Mr. Navid, muito paciente e didatico em seus ensinamentos.</p>







<h1>_____________________________________________________________</h1>



<h3>vvv  ENGLISH VERSION  vvv</h3>



<h1>_____________________________________________________________</h1>





<img src="ProjectImages\ReadmeFirstImage.PNG" alt="InventoryViewport" width="800" >


<h1>### Inventory Project ###</h1>
<h3>This project is part of a study following the course 'Unreal Engine 5 UI Design: Advanced inventory system with UE5', by instructor Mr. Navid, Unreal Magic, on Udemy.</h3>
<p>Both the course and my project are inspired by Legends of Zelda, I tried to bring different assets, but the similarity is evident.</p>

<p>This project will no longer receive updates, its purpose is to showcase my knowledge in handling Arrays and dealing with Interface, BlueprintComponents, UserInterface, including drag and drop as well as an action menu for items in different inventory tabs.</p>

<h1>### Stages ###</h1>
<p>With the goal of the project being used in future ideas, I followed the instructor's advice to keep everything modular, both files and their folders, as well as the code, using functions and components added to my player ("BP_ThirdPersonCharacter"), thus avoiding recurrent use of the "CastTo" node, which optimizes game performance and player experience.</p>

<h2>BPC_Inventory</h2>
<p>First, I created the initializations of the BlueprintComponent by adding PlayerController's MappingContext to the inventory's InputMappingContext.</p>
<p>When starting the WidgetBlueprint of the inventory, I used CastToBP_ThirdPersonCharacter to save the Player variable, used BindEventToComponentBeginOverlap in the CapsuleComponent for the collection system of what I called currency.</p>
<img src="ProjectImages\CurrencyAssets.PNG" alt="CurrencyAssets" width="400" >
<img src="ProjectImages\CurrencyAdd.PNG" alt="CurrencyAdd" width="400" >
<p>I included the health bar and currency count in the game's Viewport, and configured the inventory sizes.</p>

<h3>AddToInventory</h3>
<p>I used EnhancedInputAction IA_Interact configured to the 'E' key to call the Trace Item function, and AddToInventory</p>
<p>The TraceItemToPickUp function checks actor collision and the implementation of the BPI_Item interface within a radius of 90 units to 50 units in front of the Player and returns success.</p>
<img src="ProjectImages\BPCAddToInventoryCall.PNG" alt="BPCAddToInventoryCall" width="400" >

<p>With this, the AddToInventory function can be executed</p>
<p>This function will be executed according to the item type, defined by Enumerators.</p>
<p>Checking the inventory in a loop, correlating the item name from Trace Item, its StackSize, and correctly adding it to its Array.</p>
<p>This causes the item to be displayed in the UserInterface when the 'I' key is pressed, calling the UpdateInventoryUI function, and opening the inventory on the screen.</p>
<img src="ProjectImages\BPCAddToInventory.PNG" alt="BPCAddToInventory" width="400" >
<img src="ProjectImages\UpdateInventoryUI.PNG" alt="UpdateInventoryUI" width="400" >
<img src="ProjectImages\ReadmeFirstImage.PNG" alt="InventoryFirstImage" width="400" >
<img src="ProjectImages\FoodTab.PNG" alt="FoodTab" width="400" >
<img src="ProjectImages\QuestItemsTab.PNG" alt="QuestItemsTab" width="400" >
<img src="ProjectImages\ShieldsTab.PNG" alt="ShieldsTab" width="400" >
<img src="ProjectImages\SwordsTab.PNG" alt="SwordsTab" width="400" >

<h2>Drag and Drop</h2>
<p>For Drag and Drop, I used Unreal's OnPreviewMouseButtonDown function to detect right mouse button hold (this same function is being used for the item action menu within the slot with the left mouse button).</p>
<img src="ProjectImages\DragDropDetect.PNG" alt="DragDropDetect" width="400" >
<p>With DragDetected, the item can be removed from its Array and its variables, in Structure, and its current Index can be passed to the DragAndDropBlueprint.</p>
<img src="ProjectImages\DragDetect.PNG" alt="DragDetect" width="400" >
<p>On Drop, I first check if the same item is in that slot, this makes the item return to its old index.</p>
<p>Another case is an empty slot, or with another item, making it possible for the dropped item to be created in that index, or swap places with the item in the current position.</p>
<img src="ProjectImages\DropDetect0.PNG" alt="DropDetect" width="400" >
<p>If the item is dropped anywhere other than the slot, I created a redundancy for it to return to its original index.</p>
<img src="ProjectImages\DropInNoSlot.PNG" alt="DropInNoSlot" width="400" >

<h2>Action Menu</h2>
<p>The action button is the first button in the menu, which is created when left-clicking the item in the slot.</p>
<p>Used to Equip items in the left and right hand of the Player.</p>
<p>For the food tab, when clicking the action button, the UseEatables function is called to modify the Player's current health.</p>
<img src="ProjectImages\ActionMenuUseEquip.PNG" alt="ActionMenuUseEquip" width="400" >
<img src="ProjectImages\ActionMenuEatables.PNG" alt="ActionMenuEatables" width="400" >
<img src="ProjectImages\ActionMenu.PNG" alt="DropInNoSlot" width="400" >

<p>The cancel button simply closes the menu, but there are redundancies in this system to close when moving the mouse away from the button area.</p>
<p>The Drop button performs different checks for the type of selected item, used to unequip items when dropped.</p>
<img src="ProjectImages\ActionMenuDrop.PNG" alt="ActionMenuDrop" width="400" >

<h1>### Conclusion ###</h1>
<h3>Another project using the structure learned and documented here is in progress, which is why in some images you can see the logic already being applied, introducing a quest mechanic.</h3>
<p>I am very grateful to the course instructor Mr. Navid, very patient and didactic in his teachings.</p>


</body>