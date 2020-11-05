<h3 align="left">15 - Bloco de Notas com JavaScript</h3>
<img src="https://drive.google.com/uc?export=view&id=1bI22fxZJXmnggOMkQ_aRVLH8I7ozr3yw" width="360" />
<p align="left">Bloco de notas com textos salvos em formato Markdown, com armazenamento das notas no Local Storage do navegador.</p>

<h4 align="left">Criado com:</h4>
<p align="left">JavaScript</p>
<p align="left">Biblioteca 'Marked' para formatação do texto salvo.</p>
<p align="left">FontAwesome para ícones</p>

<h4 align="left">Como funciona?</h4>
<p align="left">O script interage diretamente com dois elementos do DOM: o botão 'Criar Nota' ('.add') e a div '.notes', que são declarados através do 'querySelector' como 'addButton' e 'notesContainer', respectivamente. Ao ser iniciado, o script verifica se há notas armazenadas no localStorage, através do método 'getItem' que executa um 'parse' no JSON e retornando-os em um array, caso positivo. Esse array é armazenado na constante 'notes' que é utilizada como condicional para executar um 'forEach' nela mesma executando, para cada nota, a função 'addNewNote' com essa nota como parâmetro. A função 'addNewNote' cria uma div com a classe 'note', através dos métodos 'createElement' e, posteriormente, 'classList.add'. Os elementos individuais do card são inclusos nela através do métodos 'innerHTML'. Após isso, quatro constantes são criadas, com o 'querySelector', para manipulação e edição da nota: 'markedText', a qual é atribuída a div '.main' onde é exibido o texto formatado; 'textEditor', a qual é atribuída a textarea onde o texto pode ser editado; 'editButton', a qual é atribuída o botão '.edit'; e 'deleteButton', a qual é atribuída o botão '.delete'. No 'editButton' é adicionado um Listener ('pointerdown') que o método 'classList.toggle' na 'markedText' e na 'textEditor', permitindo a transição entre o campo de edição e o texto salvo, além de usar esse mesmo método para substituir seu ícone (tag 'i'). A nota recebida no parâmetro da função é atribuída ao 'value' da 'textEditor' e ao 'markedText', com o 'innerHTML'. Um Listener ('input') é utilizado na 'textEditor', fazendo com que o valor substituído seja atribuído a 'markedText', com o 'innerHTML', além de executar a função 'updateLocalStorage()', que atualizada o storage com a nova nota. Na 'deleteButton' é usado um Listener ('pointerdown') que apaga a respectiva div através do método 'remove()', além de executar a função 'updateLocalStorage()', atualizando o storage, removendo a nota. A função 'addNewNote' é finalizada com o método 'appendChild' sendo utilizado na 'notesContainer', que faz com que a div criada seja adicionada como filha dela. A função 'updateLocalStorage', que atualiza os dados no storage, atribui um array com todas as textarea do documento a constante 'notesText' que é percorrida com um 'forEach', para que o valor de cada textarea seja incluso (.push()) no array 'notes', que é armazenado no storage através do método JSON.stringify. Por fim, um Listener ('pointerdown') no 'addButton' executa a função 'addNewNote', gerando um card em branco, habilitado para edição (classes dinâmicas no botão de edição, na div '.main' e na textarea fazem com que o card seja iniciado dessa maneira, caso a função 'addNewNote' seja executada com parâmetro vazio).</p>

<h4 align="left">Como executar localmente:</h4>
<p align="left">Baixe a pasta e abra o arquivo 'index.html'</p>

[Veja ao vivo](https://g31-bloco-notas.now.sh/)