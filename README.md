<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Relatório de Não Conformidade</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e74c3c;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f8f9fa;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
        }
        
        .header {
            background-color: var(--primary-color);
            color: white;
            padding: 1.5rem;
            border-radius: 8px;
            margin-bottom: 2rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        
        .form-section {
            background-color: white;
            border-radius: 8px;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
            border-left: 4px solid var(--secondary-color);
        }
        
        .form-section h3 {
            color: var(--primary-color);
            border-bottom: 1px solid #eee;
            padding-bottom: 0.5rem;
            margin-bottom: 1.5rem;
        }
        
        .table-section {
            margin-top: 1.5rem;
        }
        
        .table th {
            background-color: var(--primary-color);
            color: white;
        }
        
        .btn-primary {
            background-color: var(--secondary-color);
            border-color: var(--secondary-color);
        }
        
        .btn-danger {
            background-color: var(--accent-color);
            border-color: var(--accent-color);
        }
        
        .btn-success {
            background-color: #27ae60;
            border-color: #27ae60;
        }
        
        .action-buttons {
            position: sticky;
            bottom: 0;
            background-color: white;
            padding: 1rem;
            border-top: 1px solid #dee2e6;
            margin-top: 2rem;
            box-shadow: 0 -2px 10px rgba(0,0,0,0.1);
        }
        
        .logo {
            font-weight: bold;
            font-size: 1.5rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .required::after {
            content: " *";
            color: var(--accent-color);
        }
        
        .file-upload {
            border: 2px dashed #ccc;
            border-radius: 8px;
            padding: 1.5rem;
            text-align: center;
            margin-top: 1rem;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .file-upload:hover {
            border-color: var(--secondary-color);
            background-color: #f8f9fa;
        }
        
        .file-list {
            margin-top: 1rem;
        }
        
        .file-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0.5rem;
            background-color: #f8f9fa;
            border-radius: 4px;
            margin-bottom: 0.5rem;
        }

        .assinatura-linha {
            border-bottom: 1px solid #000;
            margin-top: 40px;
            padding-bottom: 5px;
        }

        .assinatura-nome {
            font-size: 12px;
            margin-top: 5px;
            text-align: center;
        }

        .assinatura-container {
            margin-bottom: 20px;
        }

        .assinaturas-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .btn-adicionar-assinatura {
            margin-bottom: 20px;
        }

        /* Estilos para evidências */
        .evidencia-container {
            background-color: #f8f9fa;
            border-radius: 8px;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            border-left: 4px solid var(--secondary-color);
        }

        .evidencia-header {
            display: flex;
            justify-content: between;
            align-items: center;
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 1px solid #dee2e6;
        }

        .evidencia-titulo {
            font-weight: bold;
            color: var(--primary-color);
            margin: 0;
        }

        .evidencia-descricao {
            margin-top: 1rem;
        }

        .evidencias-botoes {
            display: flex;
            gap: 10px;
            margin-bottom: 1rem;
            flex-wrap: wrap;
        }

        .btn-evidencia {
            white-space: nowrap;
        }

        .imagem-preview {
            max-width: 200px;
            max-height: 150px;
            border-radius: 4px;
            margin-right: 10px;
            margin-bottom: 10px;
            border: 1px solid #ddd;
        }

        .preview-container {
            display: flex;
            flex-wrap: wrap;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="container my-4">
        <div class="header">
            <div class="d-flex justify-content-between align-items-center">
                <div class="logo">
                    <i class="fas fa-clipboard-check"></i>
                    Relatório de Não Conformidade
                </div>
                <div class="text-end">
                    <small>Código: FO.ENG.CORP.003</small><br>
                    <small>Aprovado em: 07/01/2025 | Revisão: 0</small>
                </div>
            </div>
        </div>

        <form id="formRelatorio">
            <!-- Seção 1: Informações Básicas -->
            <div class="form-section">
                <h3><i class="fas fa-info-circle me-2"></i>Informações Básicas</h3>
                <div class="row">
                    <div class="col-md-6 mb-3">
                        <label for="dataNotificacao" class="form-label required">Data de notificação</label>
                        <input type="date" class="form-control" id="dataNotificacao" required>
                    </div>
                    <div class="col-md-6 mb-3">
                        <label for="unidade" class="form-label required">Unidade</label>
                        <input type="text" class="form-control" id="unidade" value="LEM-BA" required>
                    </div>
                </div>
                <div class="row">
                    <div class="col-md-6 mb-3">
                        <label for="projeto" class="form-label">Projeto</label>
                        <input type="text" class="form-control" id="projeto" placeholder="Nome do projeto">
                    </div>
                    <div class="col-md-6 mb-3">
                        <label for="areaSetor" class="form-label required">Área/setor</label>
                        <input type="text" class="form-control" id="areaSetor" value="BALANÇA RODOVIÁRIA" required>
                    </div>
                </div>
                <div class="mb-3">
                    <label class="form-label required">Motivo da notificação</label>
                    <div class="row">
                        <div class="col-md-3 mb-2">
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" id="motivo1" value="Aplicação de material">
                                <label class="form-check-label" for="motivo1">Aplicação de material</label>
                            </div>
                        </div>
                        <div class="col-md-3 mb-2">
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" id="motivo2" value="Efeito">
                                <label class="form-check-label" for="motivo2">Efeito</label>
                            </div>
                        </div>
                        <div class="col-md-3 mb-2">
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" id="motivo3" value="Segurança">
                                <label class="form-check-label" for="motivo3">Segurança</label>
                            </div>
                        </div>
                        <div class="col-md-3 mb-2">
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" id="motivo4" value="5 S">
                                <label class="form-check-label" for="motivo4">5 S</label>
                            </div>
                        </div>
                        <div class="col-md-3 mb-2">
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" id="motivo5" value="Armazenamento de material">
                                <label class="form-check-label" for="motivo5">Armazenamento de material</label>
                            </div>
                        </div>
                        <div class="col-md-3 mb-2">
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" id="motivo6" value="Prazo">
                                <label class="form-check-label" for="motivo6">Prazo</label>
                            </div>
                        </div>
                        <div class="col-md-3 mb-2">
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" id="motivo7" value="Outro" checked>
                                <label class="form-check-label" for="motivo7">Outro</label>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="row">
                    <div class="col-md-6 mb-3">
                        <label for="empresa" class="form-label required">Empresa</label>
                        <input type="text" class="form-control" id="empresa" value="INPASA" required>
                    </div>
                    <div class="col-md-3 mb-3">
                        <label for="responsavelEmpresa" class="form-label">Responsável Empresa</label>
                        <input type="text" class="form-control" id="responsavelEmpresa" placeholder="Nome do responsável">
                    </div>
                    <div class="col-md-3 mb-3">
                        <label for="responsavelArea" class="form-label required">Responsável Área</label>
                        <input type="text" class="form-control" id="responsavelArea" value="Isaac Farias Dos Santos" required>
                    </div>
                </div>
            </div>

            <!-- Seção 2: Situação Encontrada -->
            <div class="form-section">
                <h3><i class="fas fa-search me-2"></i>Situação Encontrada</h3>
                <div class="mb-3">
                    <label for="situacaoEncontrada" class="form-label required">Descrição do desvio</label>
                    <textarea class="form-control" id="situacaoEncontrada" rows="5" required>Para realizar a energização e utilização da BALANÇA RODOVIÁRIA, se faz necessário a conexão com um ponto de energia mais próximo. O cabo necessário para ligação de forma provisória da balança é de 4x6mm², foi verificado a utilização do cabo de 149m que veio de transferência de outra unidade, porém o cabo já está compatibilizado em outro projeto. É necessário a transferência de 65m cabo cobre PVC 4x6mm² de outra unidade ou emitir uma ordem de compra para essa utilização.</textarea>
                </div>
                
                <!-- Nova Seção de Evidências -->
                <div class="mb-3">
                    <label class="form-label">Evidências</label>
                    
                    <div class="evidencias-botoes">
                        <button type="button" class="btn btn-outline-primary btn-evidencia" onclick="adicionarEvidencia('Fotos')">
                            <i class="fas fa-camera me-1"></i> Adicionar Fotos
                        </button>
                        <button type="button" class="btn btn-outline-primary btn-evidencia" onclick="adicionarEvidencia('Documentos')">
                            <i class="fas fa-file me-1"></i> Adicionar Documentos
                        </button>
                        <button type="button" class="btn btn-outline-primary btn-evidencia" onclick="adicionarEvidencia('Laudos')">
                            <i class="fas fa-clipboard-check me-1"></i> Adicionar Laudos
                        </button>
                        <button type="button" class="btn btn-outline-primary btn-evidencia" onclick="adicionarEvidencia('Outras Evidências')">
                            <i class="fas fa-plus me-1"></i> Outras Evidências
                        </button>
                    </div>

                    <div id="containerEvidencias">
                        <!-- Evidências serão adicionadas aqui dinamicamente -->
                    </div>
                </div>
            </div>

            <!-- Seção 3: Ação Imediata -->
            <div class="form-section">
                <h3><i class="fas fa-bolt me-2"></i>Ação Imediata</h3>
                <p class="text-muted">O que foi feito para resolver o problema?</p>
                
                <div class="table-section">
                    <table class="table table-bordered" id="tabelaAcaoImediata">
                        <thead>
                            <tr>
                                <th width="40%">O que?</th>
                                <th width="30%">Por quê?</th>
                                <th width="15%">Quem?</th>
                                <th width="10%">Quando?</th>
                                <th width="5%"></th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><input type="text" class="form-control" value="Solicitar a transferência do cabo de outra unidade ou compra junto ao suprimentos"></td>
                                <td><input type="text" class="form-control" value="Realizar a ligação da balança"></td>
                                <td><input type="text" class="form-control" value="Fernando Dantas/ Gustavo Santiago"></td>
                                <td><input type="text" class="form-control" value="Imediato"></td>
                                <td class="text-center"><button type="button" class="btn btn-sm btn-danger" onclick="removerLinha(this)"><i class="fas fa-times"></i></button></td>
                            </tr>
                        </tbody>
                    </table>
                    <button type="button" class="btn btn-sm btn-primary" onclick="adicionarLinha('tabelaAcaoImediata')">
                        <i class="fas fa-plus me-1"></i> Adicionar Ação
                    </button>
                </div>
            </div>

            <!-- Seção 4: Plano de Ação para Mitigação -->
            <div class="form-section">
                <h3><i class="fas fa-tasks me-2"></i>Plano de Ação para Mitigação</h3>
                
                <div class="table-section">
                    <table class="table table-bordered" id="tabelaPlanoAcao">
                        <thead>
                            <tr>
                                <th width="35%">O que será feito?</th>
                                <th width="30%">Resultado Esperado?</th>
                                <th width="20%">Quem?</th>
                                <th width="10%">Quando?</th>
                                <th width="5%"></th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td><input type="text" class="form-control" value="Projeto e lista de materiais para rede provisória das balanças rodoviária"></td>
                                <td><input type="text" class="form-control" value="Inclusão do material em projetos futuros de redes provisórias da balança Rodoviária"></td>
                                <td><input type="text" class="form-control" value="Gustavo Simões"></td>
                                <td><input type="text" class="form-control" value="A definir em reunião para tratativa"></td>
                                <td class="text-center"><button type="button" class="btn btn-sm btn-danger" onclick="removerLinha(this)"><i class="fas fa-times"></i></button></td>
                            </tr>
                        </tbody>
                    </table>
                    <button type="button" class="btn btn-sm btn-primary" onclick="adicionarLinha('tabelaPlanoAcao')">
                        <i class="fas fa-plus me-1"></i> Adicionar Plano
                    </button>
                </div>
            </div>

            <!-- Seção 5: Assinaturas -->
            <div class="form-section">
                <h3><i class="fas fa-pen me-2"></i>Assinaturas</h3>
                
                <div class="mb-3">
                    <div class="input-group btn-adicionar-assinatura">
                        <input type="text" class="form-control" id="novaAssinatura" placeholder="Digite um novo cargo...">
                        <button type="button" class="btn btn-primary" onclick="adicionarAssinaturaPersonalizada()">
                            <i class="fas fa-plus me-1"></i> Adicionar Assinatura
                        </button>
                    </div>
                </div>

                <div class="assinaturas-grid" id="containerAssinaturas">
                    <!-- Assinaturas serão adicionadas aqui dinamicamente -->
                </div>
            </div>

            <!-- Botões de Ação -->
            <div class="action-buttons">
                <div class="d-flex justify-content-between">
                    <div>
                        <button type="button" class="btn btn-outline-secondary" id="btnSalvarRascunho">
                            <i class="fas fa-save me-1"></i> Salvar Rascunho
                        </button>
                    </div>
                    <div>
                        <button type="button" class="btn btn-success" id="btnExportarPDF">
                            <i class="fas fa-file-pdf me-1"></i> Exportar para PDF
                        </button>
                        <button type="submit" class="btn btn-primary ms-2">
                            <i class="fas fa-check me-1"></i> Finalizar Relatório
                        </button>
                    </div>
                </div>
            </div>
        </form>
    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // Arrays para armazenar dados
        let assinaturas = [];
        let evidencias = [];
        let contadorEvidencias = 0;

        // Inicialização
        document.addEventListener('DOMContentLoaded', function() {
            // Configurar botões
            document.getElementById('btnSalvarRascunho').addEventListener('click', salvarRascunho);
            document.getElementById('btnExportarPDF').addEventListener('click', exportarParaPDF);
            document.getElementById('formRelatorio').addEventListener('submit', finalizarRelatorio);
            
            // Carregar data atual
            document.getElementById('dataNotificacao').valueAsDate = new Date();

            // Adicionar algumas assinaturas padrão
            adicionarAssinatura('SUPERVISOR REGIONAL DE PROJETOS ELÉTRICOS');
        });

        // Funções para manipulação de tabelas
        function adicionarLinha(tabelaId) {
            const tabela = document.getElementById(tabelaId).getElementsByTagName('tbody')[0];
            const novaLinha = tabela.insertRow();
            
            if (tabelaId === 'tabelaAcaoImediata') {
                novaLinha.innerHTML = `
                    <td><input type="text" class="form-control" placeholder="Descreva a ação"></td>
                    <td><input type="text" class="form-control" placeholder="Justificativa"></td>
                    <td><input type="text" class="form-control" placeholder="Responsável"></td>
                    <td><input type="text" class="form-control" placeholder="Prazo"></td>
                    <td class="text-center"><button type="button" class="btn btn-sm btn-danger" onclick="removerLinha(this)"><i class="fas fa-times"></i></button></td>
                `;
            } else {
                novaLinha.innerHTML = `
                    <td><input type="text" class="form-control" placeholder="Descreva a ação"></td>
                    <td><input type="text" class="form-control" placeholder="Resultado esperado"></td>
                    <td><input type="text" class="form-control" placeholder="Responsável"></td>
                    <td><input type="text" class="form-control" placeholder="Prazo"></td>
                    <td class="text-center"><button type="button" class="btn btn-sm btn-danger" onclick="removerLinha(this)"><i class="fas fa-times"></i></button></td>
                `;
            }
        }

        function removerLinha(botao) {
            const linha = botao.closest('tr');
            linha.remove();
        }

        // Funções para gerenciar assinaturas
        function adicionarAssinatura(cargo) {
            const id = 'assinatura_' + Date.now();
            const assinatura = {
                id: id,
                cargo: cargo,
                nome: ''
            };
            
            assinaturas.push(assinatura);
            renderizarAssinaturas();
        }

        function adicionarAssinaturaPersonalizada() {
            const input = document.getElementById('novaAssinatura');
            const cargo = input.value.trim();
            
            if (cargo) {
                adicionarAssinatura(cargo);
                input.value = '';
            } else {
                alert('Por favor, digite um cargo para adicionar.');
            }
        }

        function removerAssinatura(id) {
            assinaturas = assinaturas.filter(assinatura => assinatura.id !== id);
            renderizarAssinaturas();
        }

        function atualizarNomeAssinatura(id, nome) {
            const assinatura = assinaturas.find(a => a.id === id);
            if (assinatura) {
                assinatura.nome = nome;
            }
        }

        function renderizarAssinaturas() {
            const container = document.getElementById('containerAssinaturas');
            container.innerHTML = '';

            assinaturas.forEach(assinatura => {
                const div = document.createElement('div');
                div.className = 'assinatura-container';
                div.innerHTML = `
                    <div class="assinatura-linha"></div>
                    <div class="assinatura-nome">
                        <input type="text" 
                               class="form-control form-control-sm text-center" 
                               placeholder="Nome do responsável"
                               value="${assinatura.nome}"
                               onchange="atualizarNomeAssinatura('${assinatura.id}', this.value)">
                        <small class="text-muted">${assinatura.cargo}</small>
                    </div>
                    <div class="text-center mt-2">
                        <button type="button" class="btn btn-sm btn-outline-danger" onclick="removerAssinatura('${assinatura.id}')">
                            <i class="fas fa-times me-1"></i> Remover
                        </button>
                    </div>
                `;
                container.appendChild(div);
            });
        }

        // Funções para gerenciar evidências
        function adicionarEvidencia(tipo) {
            contadorEvidencias++;
            const id = 'evidencia_' + Date.now();
            const evidencia = {
                id: id,
                tipo: tipo,
                descricao: '',
                arquivos: [],
                numero: contadorEvidencias
            };
            
            evidencias.push(evidencia);
            renderizarEvidencias();
        }

        function removerEvidencia(id) {
            evidencias = evidencias.filter(evidencia => evidencia.id !== id);
            // Reorganizar números
            evidencias.forEach((evidencia, index) => {
                evidencia.numero = index + 1;
            });
            contadorEvidencias = evidencias.length;
            renderizarEvidencias();
        }

        function atualizarDescricaoEvidencia(id, descricao) {
            const evidencia = evidencias.find(e => e.id === id);
            if (evidencia) {
                evidencia.descricao = descricao;
            }
        }

        function handleFileUploadEvidencia(event, id) {
            const files = event.target.files;
            const evidencia = evidencias.find(e => e.id === id);
            
            if (evidencia) {
                for (let i = 0; i < files.length; i++) {
                    const file = files[i];
                    evidencia.arquivos.push({
                        nome: file.name,
                        arquivo: file
                    });
                }
                renderizarEvidencias();
            }
            
            // Resetar o input
            event.target.value = '';
        }

        function removerArquivoEvidencia(id, indexArquivo) {
            const evidencia = evidencias.find(e => e.id === id);
            if (evidencia) {
                evidencia.arquivos.splice(indexArquivo, 1);
                renderizarEvidencias();
            }
        }

        function renderizarEvidencias() {
            const container = document.getElementById('containerEvidencias');
            container.innerHTML = '';

            evidencias.forEach(evidencia => {
                const div = document.createElement('div');
                div.className = 'evidencia-container';
                div.innerHTML = `
                    <div class="evidencia-header">
                        <h6 class="evidencia-titulo">${evidencia.tipo} - Figura ${evidencia.numero}</h6>
                        <button type="button" class="btn btn-sm btn-outline-danger" onclick="removerEvidencia('${evidencia.id}')">
                            <i class="fas fa-times me-1"></i> Remover
                        </button>
                    </div>
                    
                    <div class="file-upload" onclick="document.getElementById('fileInput_${evidencia.id}').click()">
                        <i class="fas fa-cloud-upload-alt fa-2x mb-2"></i>
                        <p>Arraste arquivos aqui ou clique para selecionar</p>
                        <input type="file" id="fileInput_${evidencia.id}" multiple 
                               style="display: none;" 
                               onchange="handleFileUploadEvidencia(event, '${evidencia.id}')">
                    </div>
                    
                    ${evidencia.arquivos.length > 0 ? `
                        <div class="file-list">
                            <strong>Arquivos adicionados:</strong>
                            ${evidencia.arquivos.map((arquivo, index) => `
                                <div class="file-item">
                                    <div>
                                        <i class="fas fa-file me-2"></i> ${arquivo.nome}
                                    </div>
                                    <button type="button" class="btn btn-sm btn-outline-danger" onclick="removerArquivoEvidencia('${evidencia.id}', ${index})">
                                        <i class="fas fa-times"></i>
                                    </button>
                                </div>
                            `).join('')}
                        </div>
                    ` : ''}
                    
                    <div class="evidencia-descricao">
                        <label class="form-label">Descrição da Figura ${evidencia.numero}:</label>
                        <textarea class="form-control" rows="3" 
                                  placeholder="Descreva esta evidência..."
                                  onchange="atualizarDescricaoEvidencia('${evidencia.id}', this.value)">${evidencia.descricao}</textarea>
                    </div>
                `;
                container.appendChild(div);
            });
        }

        // Funções para salvar/carregar rascunhos
        function salvarRascunho() {
            const dadosFormulario = {
                dataNotificacao: document.getElementById('dataNotificacao').value,
                unidade: document.getElementById('unidade').value,
                projeto: document.getElementById('projeto').value,
                areaSetor: document.getElementById('areaSetor').value,
                empresa: document.getElementById('empresa').value,
                responsavelEmpresa: document.getElementById('responsavelEmpresa').value,
                responsavelArea: document.getElementById('responsavelArea').value,
                situacaoEncontrada: document.getElementById('situacaoEncontrada').value,
                assinaturas: assinaturas,
                evidencias: evidencias,
                dataSalvamento: new Date().toLocaleString('pt-BR')
            };
            
            // Salvar no localStorage
            const rascunhos = JSON.parse(localStorage.getItem('rascunhosRelatorio')) || [];
            rascunhos.push(dadosFormulario);
            localStorage.setItem('rascunhosRelatorio', JSON.stringify(rascunhos));
            
            alert('Rascunho salvo com sucesso!');
        }

        // Função para exportar para PDF
        function exportarParaPDF() {
            // Validar formulário antes de exportar
            if (!validarFormulario()) {
                alert('Por favor, preencha todos os campos obrigatórios antes de exportar.');
                return;
            }
            
            // Criar conteúdo para impressão
            const conteudo = gerarConteudoPDF();
            const janelaImpressao = window.open('', '_blank');
            janelaImpressao.document.write(`
                <!DOCTYPE html>
                <html>
                <head>
                    <title>Relatório de Não Conformidade</title>
                    <style>
                        body { 
                            font-family: Arial, sans-serif; 
                            margin: 20px; 
                            line-height: 1.4;
                            font-size: 12px;
                        }
                        .header { 
                            background: #2c3e50; 
                            color: white; 
                            padding: 20px; 
                            border-radius: 8px;
                            margin-bottom: 20px;
                        }
                        .section { 
                            margin: 25px 0; 
                            padding: 15px; 
                            border-left: 4px solid #3498db; 
                            background: #f8f9fa;
                            border-radius: 5px;
                        }
                        .keep-together {
                            page-break-inside: avoid;
                            break-inside: avoid;
                        }
                        table { 
                            width: 100%; 
                            border-collapse: collapse; 
                            margin: 10px 0; 
                            font-size: 11px;
                        }
                        th, td { 
                            border: 1px solid #ddd; 
                            padding: 8px; 
                            text-align: left; 
                        }
                        th { 
                            background: #2c3e50; 
                            color: white; 
                            font-weight: bold;
                        }
                        h1 { 
                            font-size: 20px; 
                            margin: 0 0 10px 0;
                        }
                        h2 { 
                            font-size: 16px; 
                            margin: 15px 0 8px 0;
                            color: #2c3e50;
                        }
                        h3 { 
                            font-size: 14px; 
                            margin: 12px 0 6px 0;
                            color: #2c3e50;
                        }
                        p { 
                            margin: 6px 0; 
                        }
                        .item-group {
                            page-break-inside: avoid;
                            break-inside: avoid;
                            margin: 15px 0;
                        }
                        .assinatura-pdf {
                            margin: 20px 0;
                            text-align: center;
                            width: 45%;
                            display: inline-block;
                            vertical-align: top;
                        }
                        .linha-assinatura {
                            border-bottom: 1px solid #000;
                            margin: 40px 0 5px 0;
                        }
                        .nome-assinatura {
                            font-size: 11px;
                            margin: 0;
                        }
                        .cargo-assinatura {
                            font-size: 10px;
                            color: #666;
                            margin: 0;
                        }
                        .assinaturas-container {
                            display: flex;
                            flex-wrap: wrap;
                            justify-content: space-between;
                            margin-top: 20px;
                        }
                        .evidencia-pdf {
                            margin: 15px 0;
                            padding: 10px;
                            border: 1px solid #ddd;
                            border-radius: 5px;
                            background: #f9f9f9;
                        }
                        .evidencia-titulo-pdf {
                            font-weight: bold;
                            color: #2c3e50;
                            margin-bottom: 5px;
                        }
                        .evidencia-descricao-pdf {
                            margin-top: 8px;
                            font-style: italic;
                        }
                        .arquivos-lista {
                            margin-top: 5px;
                            font-size: 11px;
                        }
                        @media print {
                            .keep-together {
                                page-break-inside: avoid !important;
                                break-inside: avoid !important;
                            }
                            .item-group {
                                page-break-inside: avoid !important;
                                break-inside: avoid !important;
                            }
                            .section {
                                page-break-inside: avoid;
                                break-inside: avoid;
                            }
                        }
                    </style>
                </head>
                <body>
                    ${conteudo}
                    <script>
                        window.print();
                        setTimeout(() => {
                            window.close();
                        }, 500);
                    <\/script>
                </body>
                </html>
            `);
            janelaImpressao.document.close();
        }

        function gerarConteudoPDF() {
            return `
                <div class="header">
                    <h1>RELATÓRIO DE NÃO CONFORMIDADE</h1>
                    <p><strong>Código:</strong> FO.ENG.CORP.003 | <strong>Aprovado em:</strong> 07/01/2025 | <strong>Revisão:</strong> 0</p>
                </div>
                
                <div class="section keep-together">
                    <h2>INFORMAÇÕES BÁSICAS</h2>
                    <table>
                        <tr>
                            <td width="25%"><strong>Data de notificação:</strong></td>
                            <td width="25%">${document.getElementById('dataNotificacao').value}</td>
                            <td width="25%"><strong>Unidade:</strong></td>
                            <td width="25%">${document.getElementById('unidade').value}</td>
                        </tr>
                        <tr>
                            <td><strong>Área/setor:</strong></td>
                            <td>${document.getElementById('areaSetor').value}</td>
                            <td><strong>Empresa:</strong></td>
                            <td>${document.getElementById('empresa').value}</td>
                        </tr>
                        <tr>
                            <td><strong>Projeto:</strong></td>
                            <td>${document.getElementById('projeto').value || 'Não informado'}</td>
                            <td><strong>Responsável Área:</strong></td>
                            <td>${document.getElementById('responsavelArea').value}</td>
                        </tr>
                    </table>
                </div>
                
                <div class="section keep-together">
                    <h2>SITUAÇÃO ENCONTRADA</h2>
                    <p style="text-align: justify;">${document.getElementById('situacaoEncontrada').value}</p>
                </div>
                
                ${evidencias.length > 0 ? `
                <div class="section">
                    <h2>EVIDÊNCIAS</h2>
                    ${gerarEvidenciasPDF()}
                </div>
                ` : ''}
                
                <div class="section">
                    <h2>AÇÃO IMEDIATA</h2>
                    <p><em>O que foi feito para resolver o problema?</em></p>
                    ${gerarTabelaPDF('tabelaAcaoImediata')}
                </div>
                
                <div class="section">
                    <h2>PLANO DE AÇÃO PARA MITIGAÇÃO</h2>
                    ${gerarTabelaPDF('tabelaPlanoAcao')}
                </div>
                
                <div class="section keep-together">
                    <h2>ASSINATURAS</h2>
                    <div class="assinaturas-container">
                        ${gerarAssinaturasPDF()}
                    </div>
                </div>
                
                <div style="margin-top: 30px; padding-top: 15px; border-top: 1px solid #ccc; font-size: 10px; text-align: center;">
                    <p>Relatório gerado em: ${new Date().toLocaleString('pt-BR')}</p>
                </div>
            `;
        }

        function gerarTabelaPDF(tabelaId) {
            const tabela = document.getElementById(tabelaId);
            const linhas = tabela.getElementsByTagName('tbody')[0].getElementsByTagName('tr');
            let html = '';
            
            for (let i = 0; i < linhas.length; i++) {
                html += `<div class="item-group">`;
                html += `<table>`;
                
                if (i === 0) {
                    html += '<tr>';
                    const headers = tabela.getElementsByTagName('th');
                    for (let j = 0; j < headers.length - 1; j++) {
                        html += `<th>${headers[j].textContent}</th>`;
                    }
                    html += '</tr>';
                }
                
                html += '<tr>';
                const inputs = linhas[i].getElementsByTagName('input');
                for (let j = 0; j < inputs.length; j++) {
                    html += `<td>${inputs[j].value}</td>`;
                }
                html += '</tr>';
                
                html += `</table>`;
                html += `</div>`;
            }
            
            return html;
        }

        function gerarAssinaturasPDF() {
            let html = '';
            assinaturas.forEach(assinatura => {
                html += `
                    <div class="assinatura-pdf">
                        <div class="linha-assinatura"></div>
                        <p class="nome-assinatura">${assinatura.nome || '_________________________'}</p>
                        <p class="cargo-assinatura">${assinatura.cargo}</p>
                    </div>
                `;
            });
            return html;
        }

        function gerarEvidenciasPDF() {
            let html = '';
            evidencias.forEach(evidencia => {
                html += `
                    <div class="evidencia-pdf">
                        <div class="evidencia-titulo-pdf">Figura ${evidencia.numero} - ${evidencia.tipo}</div>
                        ${evidencia.arquivos.length > 0 ? `
                            <div class="arquivos-lista">
                                <strong>Arquivos:</strong> ${evidencia.arquivos.map(arquivo => arquivo.nome).join(', ')}
                            </div>
                        ` : ''}
                        ${evidencia.descricao ? `
                            <div class="evidencia-descricao-pdf">
                                <strong>Descrição:</strong> ${evidencia.descricao}
                            </div>
                        ` : ''}
                    </div>
                `;
            });
            return html;
        }

        // Função para validar formulário
        function validarFormulario() {
            const camposObrigatorios = document.querySelectorAll('[required]');
            let valido = true;
            
            camposObrigatorios.forEach(campo => {
                if (!campo.value.trim()) {
                    campo.classList.add('is-invalid');
                    valido = false;
                } else {
                    campo.classList.remove('is-invalid');
                }
            });
            
            return valido;
        }

        // Função para finalizar relatório
        function finalizarRelatorio(event) {
            event.preventDefault();
            
            if (!validarFormulario()) {
                alert('Por favor, preencha todos os campos obrigatórios.');
                return;
            }
            
            alert('Relatório finalizado com sucesso!');
        }
    </script>
</body>
</html>
