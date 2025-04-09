<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Linha 6</title>
    <style>
        body {
            font-family: sans-serif;
            margin: 0;
            background-color: #f0f0f0;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }

        /* Estilos para a página de login */
        .login-container {
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            padding: 30px;
            width: 350px;
            text-align: center;
            margin-top: 20px;
        }

        .login-container h2 {
            margin-bottom: 20px;
        }

        .login-container .entrada {
            margin-bottom: 15px;
        }

        .login-container label {
            display: block;
            margin-bottom: 5px;
        }

        .login-container input[type="text"],
        .login-container input[type="password"] {
            width: calc(100% - 16px);
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .login-container button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 15px;
        }

        .login-container button:hover {
            background-color: #0056b3;
        }

        .login-container .erro-mensagem, .login-container .sucesso-mensagem, .login-container .info-mensagem {
            margin-top: 10px;
            text-align: center;
        }

        .login-container .erro-mensagem {
            color: red;
        }

        .login-container .sucesso-mensagem {
            color: green;
        }

        .login-container .info-mensagem {
            color: #007bff;
            font-size: 0.9em;
            margin-bottom: 15px;
        }

        .login-container #registro-container {
            display: none;
            margin-top: 20px;
            border-top: 1px solid #eee;
            padding-top: 20px;
        }

        .login-container #registro-container h3 {
            margin-bottom: 10px;
        }

        .login-container #registro-container button {
            margin-top: 10px;
        }

        #registros-admin {
            margin-top: 20px;
            padding: 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f9f9f9;
            text-align: left;
            display: none; /* Oculto por padrão */
        }

        #registros-admin h3 {
            margin-top: 0;
            margin-bottom: 10px;
            text-align: center;
        }

        #registros-admin ul {
            list-style: none;
            padding: 0;
        }

        #registros-admin ul li {
            padding: 5px 0;
            border-bottom: 1px dotted #ddd;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        #registros-admin ul li:last-child {
            border-bottom: none;
        }

        #registros-admin ul li button {
            background-color: #dc3545;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 5px 10px;
            cursor: pointer;
            font-size: 0.9em;
            margin-left: 5px;
        }

        #registros-admin ul li button:hover {
            background-color: #c82333;
        }

        /* Estilos para a navegação */
        .navigation {
            display: flex;
            margin: 20px 0;
        }

        .navigation button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 0 10px;
        }

        .navigation button:hover {
            background-color: #0056b3;
        }

        /* Estilos para a calculadora (inicialmente escondida) */
        .calculadora-container, .controle-hora-container, .usuarios-registrados-container {
            display: none; /* Esconde as seções inicialmente */
            align-items: center;
            flex-direction: column;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            padding: 20px;
            margin-bottom: 20px;
            width: 80%;
            max-width: 800px;
        }

        .usuarios-registrados-container h2 {
            text-align: center;
            margin-bottom: 15px;
        }

        .usuarios-registrados-container ul {
            list-style: none;
            padding: 0;
            width: 100%;
            max-width: 400px;
        }

        .usuarios-registrados-container ul li {
            padding: 8px 0;
            border-bottom: 1px dotted #ccc;
            text-align: center;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .usuarios-registrados-container ul li:last-child {
            border-bottom: none;
        }

        .usuarios-registrados-container ul li button {
            background-color: #ffc107;
            color: #212529;
            border: none;
            border-radius: 5px;
            padding: 5px 10px;
            cursor: pointer;
            font-size: 0.9em;
            margin-left: 5px;
        }

        .usuarios-registrados-container ul li button:hover {
            background-color: #e0a800;
        }

        .usuarios-registrados-container ul li .excluir-btn {
            background-color: #dc3545;
            color: white;
        }

        .usuarios-registrados-container ul li .excluir-btn:hover {
            background-color: #c82333;
        }

        .calculadora {
            width: 100%;
            max-width: 300px;
            margin-bottom: 20px;
        }

        .calculadora h2 {
            text-align: center;
        }

        .calculadora .entrada {
            margin-bottom: 10px;
        }

        .calculadora label {
            display: block;
            margin-bottom: 5px;
        }

        .calculadora input[type="number"] {
            width: 100%;
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .calculadora .botoes {
            text-align: center;
            margin-top: 15px;
        }

        .calculadora button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .calculadora button:hover {
            background-color: #0056b3;
        }

        .calculadora .resultado {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            text-align: center;
        }

        .calculadora h3 {
            margin-top: 0;
        }

        /* Estilos para a tabela de controle hora a hora */
        .controle-hora-container h1 {
            text-align: center;
        }

        .controle-hora-container .date-control {
            display: flex;
            align-items: center;
            margin-bottom: 10px;
        }

        .controle-hora-container .date-control label {
            margin-right: 10px;
        }

        .controle-hora-container .date-control input[type="date"] {
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            margin-right: 10px;
        }

        .controle-hora-container .date-control button {
            padding: 8px 15px;
            font-size: 14px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .controle-hora-container .date-control button:hover {
            background-color: #218838;
        }

        .controle-hora-container table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
        }

        .controle-hora-container th, .controle-hora-container td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: center;
        }

        .controle-hora-container th {
            background-color: #f0f0f0;
        }

        .controle-hora-container .edit-input {
            width: 80px;
            padding: 5px;
            text-align: center;
        }

        .controle-hora-container .comment-input {
            width: 100%;
            padding: 5px;
        }

        .controle-hora-container .acoes button {
            padding: 8px 12px;
            margin: 5px;
            cursor: pointer;
            border: none;
            border-radius: 4px;
            background-color: #007bff;
            color: white;
        }

        .controle-hora-container .acoes button:hover {
            background-color: #0056b3;
        }

        .controle-hora-container .total-producao {
            margin-top: 20px;
            font-weight: bold;
            text-align: right;
        }

        .controle-hora-container .meta-atingida {
            background-color: #d4edda !important; /* Verde claro */
            color: #155724;
        }

        .controle-hora-container .meta-nao-atingida {
            background-color: #f8d7da !important; /* Vermelho claro */
            color: #721c24;
        }

        .creditos {
            font-size: 0.8em;
            color: #777;
            text-align: center;
            margin-top: 20px;
        }

        .edit-password-container {
            display: none;
            margin-left: 10px;
        }

        .edit-password-container input[type="password"] {
            padding: 5px;
            border: 1px solid #ccc;
            border-radius: 4px;
            margin-right: 5px;
        }

        .edit-password-container button {
            padding: 5px 10px;
            font-size: 0.9em;
            border-radius: 5px;
            cursor: pointer;
            margin-left: 5px;
        }

        .edit-password-container .salvar-btn {
            background-color: #28a745;
            color: white;
            border: none;
        }

        .edit-password-container .salvar-btn:hover {
            background-color: #218838;
        }

        .edit-password-container .cancelar-btn {
            background-color: #6c757d;
            color: white;
            border: none;
        }

        .edit-password-container .cancelar-btn:hover {
            background-color: #5a6268;
        }
    </style>
</head>
<body>

    <div class="login-container" id="login-container">
        <h2>Login</h2>
        <div class="info-mensagem">Para registrar, utilize seu RE (somente números).</div>
        <div class="entrada">
            <label for="login">RE:</label>
            <input type="text" id="login" placeholder="Digite seu RE" oninput="this.value = this.value.replace(/[^0-9]/g, '');">
        </div>
        <div class="entrada">
            <label for="senha">Senha:</label>
            <input type="password" id="senha" placeholder="Digite sua senha">
        </div>
        <button onclick="verificarLogin()">Entrar</button>
        <p id="erro-mensagem" class="erro-mensagem"></p>
        <p id="sucesso-mensagem" class="sucesso-mensagem" style="display: none;">Registrado com sucesso!</p>

        <div id="registro-container">
            <h3>Registre-se</h3>
            <div class="entrada">
                <label for="novo_re">RE:</label>
                <input type="text" id="novo_re" placeholder="Digite seu RE (somente números)" oninput="this.value = this.value.replace(/[^0-9]/g, '');">
            </div>
            <div class="entrada">
                <label for="nova_senha">Senha:</label>
                <input type="password" id="nova_senha" placeholder="Digite sua senha">
            </div>
            <button onclick="registrarUsuario()">Registrar</button>
            <p id="registro-erro-mensagem" class="erro-mensagem"></p>
            <p id="registro-sucesso-mensagem" class="sucesso-mensagem" style="display: none;">Registrado com sucesso!</p>
        </div>

        <button onclick="mostrarRegistroForm()">Registrar-se</button>

        <div id="registros-admin">
            <h3>Registro dos Usuarios</h3>
            <ul id="lista-registros">
            </ul>
        </div>
    </div>

    <div id="app-content" style="display: none; align-items: center; flex-direction: column;">
        <div class="navigation" id="app-navigation">
            <button onclick="mostrarCalculadora()">Calculadora</button>
            <button onclick="mostrarControleHora()">Controle Hora a Hora</button>
            <button onclick="logout()">Sair</button>
        </div>

        <div class="calculadora-container" id="calculadora-container">
            <div class="calculadora">
                <h2>Calculadora de Produção</h2>

                <div class="entrada">
                    <label for="meta_producao_calc">Meta de Produção:</label>
                    <input type="number" id="meta_producao_calc" placeholder="Digite a meta de produção">
                </div>

                <div class="entrada">
                    <label for="producao_dia_calc">Produção do Dia:</label>
                    <input type="number" id="producao_dia_calc" placeholder="Digite a produção do dia">
                </div>

                <div class="botoes">
                    <button onclick="calcularResultado()">Calcular</button>
                </div>

                <div class="resultado">
                    <h3>Resultado:</h3>
                    <p id="resultado"></p>
                </div>
            </div>
        </div>

        <div class="controle-hora-container" id="controle-hora-container">
            <h1>Controle de Produção de Paletes por Hora</h1>
            <div class="date-control">
                <label for="data-producao">Selecionar Data:</label>
                <input type="date" id="data-producao">
                <button onclick="salvarDataProducao()">Salvar Data</button>
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Horário</th>
                        <th>Paletes Produzidos</th>
                        <th>Comentários</th>
                        <th>Ações</th>
                    </tr>
                </thead>
                <tbody id="producao-table-body">
                </tbody>
            </table>

            <div class="total-producao">
                Total de Paletes Produzidos: <span id="total-paletes">0</span>
            </div>
        </div>

        <div class="usuarios-registrados-container" id="usuarios-registrados-container">
            <h2>Usuarios Registrados</h2>
            <ul id="lista-usuarios-registrados">
            </ul>
            <p id="permissao-negada" style="color: red; display: none;">Você não tem permissão para ver esta seção.</p>
        </div>

        <div class="creditos">
            Programado por Raul Castro
        </div>
    </div>

    <script>
        const loginContainer = document.getElementById('login-container');
        const appContent = document.getElementById('app-content');
        const calculadoraContainer = document.getElementById('calculadora-container');
        const controleHoraContainer = document.getElementById('controle-hora-container');
        const loginInput = document.getElementById('login');
        const senhaInput = document.getElementById('senha');
        const erroMensagem = document.getElementById('erro-mensagem');
        const sucessoMensagem = document.getElementById('sucesso-mensagem');
        const registroContainer = document.getElementById('registro-container');
        const novoReInput = document.getElementById('novo_re');
        const novaSenhaInput = document.getElementById('nova_senha');
        const registroErroMensagem = document.getElementById('registro-erro-mensagem');
        const registroSucessoMensagem = document.getElementById('registro-sucesso-mensagem');
        const registrosAdminDiv = document.getElementById('registros-admin');
        const listaRegistrosUl = document.getElementById('lista-registros');
        const usuariosRegistradosContainer = document.getElementById('usuarios-registrados-container');
        const listaUsuariosRegistradosUl = document.getElementById('lista-usuarios-registrados');
        const permissaoNegadaParagrafo = document.getElementById('permissao-negada');
        const appNavigation = document.getElementById('app-navigation');

        // Elementos da calculadora
        const metaProducaoCalcInput = document.getElementById('meta_producao_calc');
        const producaoDiaCalcInput = document.getElementById('producao_dia_calc');
        const resultadoCalculadora = document.getElementById('resultado');

        // Elementos do controle hora a hora
        const controleHoraContainerDiv = document.getElementById('controle-hora-container');
        const dataProducaoInput = document.getElementById('data-producao');
        const tabelaProducaoBody = document.getElementById('producao-table-body');
        const totalPaletesSpan = document.getElementById('total-paletes');
        let metaPaletesHora = 50;
        const horariosProducao = ["05:00 ás 06:00", "06:00 ás 07:00", "07:00 ás 08:00", "08:00 ás 09:00", "09:00 ás 10:00", "10:00 ás 11:00", "12:00 á 13:20"];

        // Banco de dados simulado no localStorage
        const DB_KEY = 'usuariosRegistrados';
        const PRODUCAO_KEY = 'producaoPorData';
        const ADMIN_LOGIN = '07051996';
        const ADMIN_SENHA = '969807';
        const RE_PERMITIDO_VER_USUARIOS = '5380422';
        let usuarioLogadoRE = null;
        let dataSelecionada = null;

        function getUsuariosRegistrados() {
            const data = localStorage.getItem(DB_KEY);
            return data ? JSON.parse(data) : [];
        }

        function salvarUsuariosRegistrados(usuarios) {
            localStorage.setItem(DB_KEY, JSON.stringify(usuarios));
        }

        function getProducaoPorData() {
            const data = localStorage.getItem(PRODUCAO_KEY);
            return data ? JSON.parse(data) : {};
        }

        function salvarProducaoPorData(producaoData) {
            localStorage.setItem(PRODUCAO_KEY, JSON.stringify(producaoData));
        }

        function mostrarRegistroForm() {
            registroContainer.style.display = 'block';
        }

        function registrarUsuario() {
            const novoRe = novoReInput.value.trim();
            const novaSenha = novaSenhaInput.value.trim();

            registroErroMensagem.textContent = '';
            registroSucessoMensagem.style.display = 'none';

            if (!novoRe || !novaSenha) {
                registroErroMensagem.textContent = 'Por favor, preencha todos os campos.';
                return;
            }

            const usuarios = getUsuariosRegistrados();
            if (usuarios.some(user => user.re === novoRe)) {
                registroErroMensagem.textContent = 'Este RE já está registrado.';
                return;
            }

            usuarios.push({ re: novoRe, senha: novaSenha });
            salvarUsuariosRegistrados(usuarios);
            registroSucessoMensagem.style.display = 'block';
            novoReInput.value = '';
            novaSenhaInput.value = '';
            registroContainer.style.display = 'none';
        }

        function verificarLogin() {
            const loginDigitado = loginInput.value.trim();
            const senhaDigitada = senhaInput.value.trim();

            erroMensagem.textContent = '';
            sucessoMensagem.style.display = 'none';
            registrosAdminDiv.style.display = 'none';
            appContent.style.display = 'none';
            loginContainer.style.display = 'flex';
            usuarioLogadoRE = null; // Limpa o RE do usuário logado

            // Remove o botão de usuários registrados se já existir
            const usuariosRegistradosButton = document.getElementById('usuarios-registrados-button');
            if (usuariosRegistradosButton) {
                appNavigation.removeChild(usuariosRegistradosButton);
            }

            if (loginDigitado === ADMIN_LOGIN && senhaDigitada === ADMIN_SENHA) {
                // Login do administrador
                const usuarios = getUsuariosRegistrados();
                listaRegistrosUl.innerHTML = '';
                if (usuarios.length > 0) {
                    usuarios.forEach(user => {
                        const li = document.createElement('li');
                        li.innerHTML = `RE: ${user.re} <button onclick="excluirUsuario('${user.re}')">Excluir</button>`;
                        listaRegistrosUl.appendChild(li);
                    });
                    registrosAdminDiv.style.display = 'block';
                } else {
                    listaRegistrosUl.innerHTML = '<li>Nenhum usuário registrado ainda.</li>';
                    registrosAdminDiv.style.display = 'block';
                }
                loginContainer.style.display = 'none';
                return;
            }

            const usuarios = getUsuariosRegistrados();
            const usuarioLogado = usuarios.find(user => user.re === loginDigitado && user.senha === senhaDigitada);

            if (usuarioLogado) {
                usuarioLogadoRE = usuarioLogado.re; // Armazena o RE do usuário logado
                loginContainer.style.display = 'none';
                appContent.style.display = 'flex';
                mostrarCalculadora();
                alert("Bem vindos ao aplicativo beta da linha 6!");

                // Adiciona o botão de usuários registrados apenas para o RE permitido
                if (usuarioLogadoRE === RE_PERMITIDO_VER_USUARIOS) {
                    const btnUsuariosRegistrados = document.createElement('button');
                    btnUsuariosRegistrados.textContent = 'Usuarios Registrados';
                    btnUsuariosRegistrados.onclick = mostrarUsuariosRegistrados;
                    btnUsuariosRegistrados.id = 'usuarios-registrados-button'; // Adiciona um ID para facilitar a remoção futura
                    appNavigation.appendChild(btnUsuariosRegistrados);
                }
            } else {
                erroMensagem.textContent = "RE ou senha incorretos.";
            }
        }

        function excluirUsuario(reParaExcluir) {
            const usuarios = getUsuariosRegistrados();
            const novosUsuarios = usuarios.filter(user => user.re !== reParaExcluir);
            salvarUsuariosRegistrados(novosUsuarios);
            // Atualiza a lista de usuários exibida para o administrador
            verificarLogin();
        }

        function mostrarCalculadora() {
            calculadoraContainer.style.display = 'flex';
            controleHoraContainer.style.display = 'none';
            usuariosRegistradosContainer.style.display = 'none';
            permissaoNegadaParagrafo.style.display = 'none';
        }

        function mostrarControleHora() {
            calculadoraContainer.style.display = 'none';
            controleHoraContainer.style.display = 'flex';
            usuariosRegistradosContainer.style.display = 'none';
            permissaoNegadaParagrafo.style.display = 'none';
            dataSelecionada = dataProducaoInput.value;
            if (!dataSelecionada) {
                const today = new Date();
                const year = today.getFullYear();
                const month = String(today.getMonth() + 1).padStart(2, '0');
                const day = String(today.getDate()).padStart(2, '0');
                dataSelecionada = `${year}-${month}-${day}`;
                dataProducaoInput.value = dataSelecionada;
            }
            carregarProducaoDoDia(dataSelecionada);
        }

        function salvarDataProducao() {
            dataSelecionada = dataProducaoInput.value;
            if (dataSelecionada) {
                salvarProducaoDoDia(dataSelecionada);
            } else {
                alert("Por favor, selecione uma data.");
            }
        }

        function carregarProducaoDoDia(data) {
            tabelaProducaoBody.innerHTML = '';
            const producaoData = getProducaoPorData();
            const producaoDoDia = producaoData[data] || Array(horariosProducao.length).fill({ paletes: 0, comentario: '' });

            totalPaletesSpan.textContent = 0;

            horariosProducao.forEach((horario, index) => {
                const rowData = producaoDoDia[index] || { paletes: 0, comentario: '' };
                const row = tabelaProducaoBody.insertRow();
                row.insertCell().textContent = horario;
                const paletesCell = row.insertCell();
                paletesCell.dataset.paletes = '';
                const paletesInput = document.createElement('input');
                paletesInput.type = 'number';
                paletesInput.classList.add('edit-input');
                paletesInput.value = rowData.paletes;
                paletesInput.min = '0';
                paletesCell.appendChild(paletesInput);

                const comentarioCell = row.insertCell();
                const comentarioInput = document.createElement('input');
                comentarioInput.type = 'text';
                comentarioInput.classList.add('comment-input');
                comentarioInput.value = rowData.comentario;
                comentarioCell.appendChild(comentarioInput);

                const acoesCell = row.insertCell();
                const editarButton = document.createElement('button');
                editarButton.textContent = 'Editar';
                editarButton.onclick = function() { editarLinha(this); };
                acoesCell.appendChild(editarButton);
            });
            atualizarTotal();
            aplicarCores();
            // Após carregar, verifica se já existe produção salva para desabilitar a edição
            if (producaoData[data] && producaoData[data].length > 0) {
                desabilitarEdicao();
            }
        }

        function salvarProducaoDoDia(data) {
            const producaoData = getProducaoPorData();
            producaoData[data] = [];
            for (let i = 0; i < tabelaProducaoBody.rows.length; i++) {
                const row = tabelaProducaoBody.rows[i];
                const paletesInput = row.cells[1].querySelector('.edit-input');
                const comentarioInput = row.cells[2].querySelector('.comment-input');
                producaoData[data].push({ paletes: parseInt(paletesInput.value) || 0, comentario: comentarioInput.value });
            }
            salvarProducaoPorData(producaoData);
            alert(`Produção do dia ${data} salva!`);
            atualizarTotal();
            aplicarCores();
            desabilitarEdicao(); // Desabilita a edição após salvar
        }

        function desabilitarEdicao() {
            for (let i = 0; i < tabelaProducaoBody.rows.length; i++) {
                const row = tabelaProducaoBody.rows[i];
                const paletesInput = row.cells[1].querySelector('.edit-input');
                const comentarioInput = row.cells[2].querySelector('.comment-input');
                const acoesCell = row.cells[3];

                paletesInput.disabled = true;
                comentarioInput.disabled = true;
                acoesCell.innerHTML = ''; // Remove os botões de ação
            }
        }

        function mostrarUsuariosRegistrados() {
            calculadoraContainer.style.display = 'none';
            controleHoraContainer.style.display = 'none';
            usuariosRegistradosContainer.style.display = 'flex';
            permissaoNegadaParagrafo.style.display = 'none';
            listaUsuariosRegistradosUl.innerHTML = '';

            if (usuarioLogadoRE === RE_PERMITIDO_VER_USUARIOS) {
                const usuarios = getUsuariosRegistrados();
                if (usuarios.length > 0) {
                    usuarios.forEach(user => {
                        const li = document.createElement('li');
                        li.innerHTML = `
                            RE: ${user.re}
                            <button onclick="editarRegistro('${user.re}', this)">Editar</button>
                            <button class="excluir-btn" onclick="excluirRegistro('${user.re}')">Excluir</button>
                            <div class="edit-password-container">
                                <input type="password" placeholder="Nova Senha">
                                <button class="salvar-btn" onclick="salvarRegistro('${user.re}', this)">Salvar</button>
                                <button class="cancelar-btn" onclick="cancelarEdicao(this)">Cancelar</button>
                            </div>
                        `;
                        listaUsuariosRegistradosUl.appendChild(li);
                    });
                } else {
                    listaUsuariosRegistradosUl.innerHTML = '<li>Nenhum usuário registrado ainda.</li>';
                }
            } else {
                usuariosRegistradosContainer.style.display = 'none';
                permissaoNegadaParagrafo.style.display = 'block';
            }
        }

        function editarRegistro(reParaEditar, botaoEditar) {
            const listItem = botaoEditar.parentNode;
            const editContainer = listItem.querySelector('.edit-password-container');
            editContainer.style.display = 'inline-block';
            botaoEditar.style.display = 'none';
            listItem.querySelector('.excluir-btn').style.display = 'none';
        }

        function salvarRegistro(reParaSalvar, botaoSalvar) {
            const listItem = botaoSalvar.parentNode.parentNode;
            const novaSenhaInput = listItem.querySelector('input[type="password"]');
            const novaSenha = novaSenhaInput.value.trim();

            if (novaSenha) {
                const usuarios = getUsuariosRegistrados();
                const index = usuarios.findIndex(user => user.re === reParaSalvar);
                if (index !== -1) {
                    usuarios[index].senha = novaSenha;
                    salvarUsuariosRegistrados(usuarios);
                    mostrarUsuariosRegistrados(); // Refresh the list
                }
            } else {
                alert("Por favor, digite a nova senha.");
            }
        }

        function cancelarEdicao(botaoCancelar) {
            const listItem = botaoCancelar.parentNode.parentNode;
            const editContainer = listItem.querySelector('.edit-password-container');
            editContainer.style.display = 'none';
            const botoesAcao = listItem.querySelectorAll('button');
            botoesAcao[0].style.display = 'inline-block'; // Botão Editar
            botoesAcao[1].style.display = 'inline-block'; // Botão Excluir
        }

        function excluirRegistro(reParaExcluir) {
            if (confirm(`Tem certeza que deseja excluir o registro do RE: ${reParaExcluir}?`)) {
                const usuarios = getUsuariosRegistrados();
                const novosUsuarios = usuarios.filter(user => user.re !== reParaExcluir);
                salvarUsuariosRegistrados(novosUsuarios);
                mostrarUsuariosRegistrados(); // Refresh the list
            }
        }

        function calcularResultado() {
            const metaProducao = parseInt(metaProducaoCalcInput.value);
            const producaoDia = parseInt(producaoDiaCalcInput.value);

            if (isNaN(metaProducao) || isNaN(producaoDia)) {
                resultadoCalculadora.textContent = "Por favor, digite números válidos.";
                return;
            }

            const subtracao = metaProducao - producaoDia;
            const resultadoFinal = subtracao / 600;

            resultadoCalculadora.textContent = `${resultadoFinal.toFixed(2)}`;
        }

        function editarLinha(botaoEditar) {
            const linha = botaoEditar.parentNode.parentNode;
            const paletesInput = linha.cells[1].querySelector('.edit-input');
            const comentarioInput = linha.cells[2].querySelector('.comment-input');
            const acoesCell = linha.cells[3];

            paletesInput.disabled = false;
            comentarioInput.disabled = false;

            const salvarButton = document.createElement('button');
            salvarButton.textContent = 'Salvar';
            salvarButton.onclick = function() { salvarEdicaoLinha(this); };

            const cancelarButton = document.createElement('button');
            cancelarButton.textContent = 'Cancelar';
            cancelarButton.onclick = function() { cancelarEdicaoLinha(this); };

            acoesCell.innerHTML = '';
            acoesCell.appendChild(salvarButton);
            acoesCell.appendChild(cancelarButton);
        }

        function salvarEdicaoLinha(botaoSalvar) {
            const linha = botaoSalvar.parentNode.parentNode;
            const horario = linha.cells[0].textContent;
            const paletesInput = linha.cells[1].querySelector('.edit-input');
            const comentarioInput = linha.cells[2].querySelector('.comment-input');
            const acoesCell = linha.cells[3];

            const paletes = parseInt(paletesInput.value) || 0;
            const comentario = comentarioInput.value;

            const producaoData = getProducaoPorData();
            if (producaoData[dataSelecionada]) {
                const index = horariosProducao.indexOf(horario);
                if (index !== -1) {
                    producaoData[dataSelecionada][index] = { paletes: paletes, comentario: comentario };
                }
            }
            salvarProducaoPorData(producaoData);
            carregarProducaoDoDia(dataSelecionada); // Recarrega a tabela para refletir as mudanças
        }

        function cancelarEdicaoLinha(botaoCancelar) {
            carregarProducaoDoDia(dataSelecionada); // Simplesmente recarrega a tabela para desfazer as edições
        }

        function atualizarTotal() {
            let total = 0;
            for (let i = 0; i < tabelaProducaoBody.rows.length; i++) {
                const paletesInput = tabelaProducaoBody.rows[i].cells[1].querySelector('.edit-input');
                total += parseInt(paletesInput.value) || 0;
            }
            totalPaletesSpan.textContent = total;
        }

        function aplicarCores() {
            for (let i = 0; i < tabelaProducaoBody.rows.length; i++) {
                const row = tabelaProducaoBody.rows[i];
                const paletesProduzidos = parseInt(row.cells[1].querySelector('.edit-input').value) || 0;
                if (paletesProduzidos >= metaPaletesHora) {
                    row.classList.add('meta-atingida');
                    row.classList.remove('meta-nao-atingida');
                } else {
                    row.classList.remove('meta-atingida');
                    row.classList.add('meta-nao-atingida');
                }
            }
        }

        function logout() {
            usuarioLogadoRE = null;
            loginContainer.style.display = 'flex';
            appContent.style.display = 'none';
            registrosAdminDiv.style.display = 'none';
            // Remove o botão de usuários registrados ao fazer logout
            const usuariosRegistradosButton = document.getElementById('usuarios-registrados-button');
            if (usuariosRegistradosButton) {
                appNavigation.removeChild(usuariosRegistradosButton);
            }
        }

        // Carrega a produção do dia atual ao exibir o controle hora a hora
        dataProducaoInput.addEventListener('change', function() {
            dataSelecionada = this.value;
            carregarProducaoDoDia(dataSelecionada);
        });

        // Inicialização: Se já estiver logado, mostrar o app
        if (usuarioLogadoRE) {
            loginContainer.style.display = 'none';
            appContent.style.display = 'flex';
            mostrarCalculadora();
        } else {
            mostrarControleHora(); // Carrega a tabela vazia na inicialização
        }
    </script>
</body>
</html>
