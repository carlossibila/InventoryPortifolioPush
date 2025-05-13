<body>

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

</body>