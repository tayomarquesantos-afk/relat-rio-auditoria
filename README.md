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
                <div class="mb-3">
                    <label class="form-label">Evidências (imagens, documentos)</label>
                    <div class="file-upload" id="fileUploadArea">
                        <i class="fas fa-cloud-upload-alt fa-2x mb-2"></i>
                        <p>Arraste arquivos aqui ou clique para selecionar</p>
                        <input type="file" id="fileInput" multiple style="display: none;">
                    </div>
                    <div class="file-list" id="fileList">
                        <!-- Lista de arquivos será adicionada aqui -->
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
                <div class="row">
                    <div class="col-md-6 mb-3">
                        <label for="assinatura1" class="form-label">Responsável 1</label>
                        <input type="text" class="form-control" id="assinatura1" value="Isaac F. Dos Santos - Esp. montagem projetos elétricos">
                    </div>
                    <div class="col-md-6 mb-3">
                        <label for="assinatura2" class="form-label">Responsável 2</label>
                        <input type="text" class="form-control" id="assinatura2" value="Leonardo Antonio Godol - SUP. REG. OBRAS ELÉT. INST.">
                    </div>
                </div>
                <div class="row">
                    <div class="col-md-6 mb-3">
                        <label for="assinatura3" class="form-label">Responsável 3</label>
                        <input type="text" class="form-control" id="assinatura3" value="Taxomarque dos Santos Cruz - Esp. Aud. Elétrica e Instr.">
                    </div>
                    <div class="col-md-6 mb-3">
                        <label for="assinatura4" class="form-label">Responsável 4</label>
                        <input type="text" class="form-control" id="assinatura4" value="Gustavo V. Simoes - SUPERVISOR PROJETOS ELETRICOS">
                    </div>
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
        // Inicialização
        document.addEventListener('DOMContentLoaded', function() {
            // Configurar upload de arquivos
            const fileUploadArea = document.getElementById('fileUploadArea');
            const fileInput = document.getElementById('fileInput');
            
            fileUploadArea.addEventListener('click', () => fileInput.click());
            fileInput.addEventListener('change', handleFileUpload);
            
            // Configurar botões
            document.getElementById('btnSalvarRascunho').addEventListener('click', salvarRascunho);
            document.getElementById('btnExportarPDF').addEventListener('click', exportarParaPDF);
            document.getElementById('formRelatorio').addEventListener('submit', finalizarRelatorio);
            
            // Carregar data atual
            document.getElementById('dataNotificacao').valueAsDate = new Date();
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

        // Funções para upload de arquivos
        function handleFileUpload(event) {
            const files = event.target.files;
            const fileList = document.getElementById('fileList');
            
            for (let i = 0; i < files.length; i++) {
                const file = files[i];
                const fileItem = document.createElement('div');
                fileItem.className = 'file-item';
                fileItem.innerHTML = `
                    <div>
                        <i class="fas fa-file me-2"></i> ${file.name}
                    </div>
                    <button type="button" class="btn btn-sm btn-outline-danger" onclick="removerArquivo(this)">
                        <i class="fas fa-times"></i>
                    </button>
                `;
                fileList.appendChild(fileItem);
            }
            
            // Resetar o input para permitir selecionar o mesmo arquivo novamente
            event.target.value = '';
        }

        function removerArquivo(botao) {
            const fileItem = botao.closest('.file-item');
            fileItem.remove();
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
                        body { font-family: Arial, sans-serif; margin: 20px; }
                        .header { background: #2c3e50; color: white; padding: 20px; border-radius: 8px; }
                        .section { margin: 20px 0; padding: 15px; border-left: 4px solid #3498db; background: #f8f9fa; }
                        table { width: 100%; border-collapse: collapse; margin: 10px 0; }
                        th, td { border: 1px solid #ddd; padding: 8px; text-align: left; }
                        th { background: #2c3e50; color: white; }
                    </style>
                </head>
                <body>
                    ${conteudo}
                    <script>
                        window.print();
                        setTimeout(() => window.close(), 1000);
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
                    <p>Código: FO.ENG.CORP.003 | Aprovado em: 07/01/2025 | Revisão: 0</p>
                </div>
                
                <div class="section">
                    <h3>Informações Básicas</h3>
                    <p><strong>Data de notificação:</strong> ${document.getElementById('dataNotificacao').value}</p>
                    <p><strong>Unidade:</strong> ${document.getElementById('unidade').value}</p>
                    <p><strong>Área/setor:</strong> ${document.getElementById('areaSetor').value}</p>
                    <p><strong>Empresa:</strong> ${document.getElementById('empresa').value}</p>
                </div>
                
                <div class="section">
                    <h3>Situação Encontrada</h3>
                    <p>${document.getElementById('situacaoEncontrada').value}</p>
                </div>
                
                <div class="section">
                    <h3>Ação Imediata</h3>
                    ${gerarTabelaPDF('tabelaAcaoImediata')}
                </div>
                
                <div class="section">
                    <h3>Plano de Ação para Mitigação</h3>
                    ${gerarTabelaPDF('tabelaPlanoAcao')}
                </div>
                
                <div class="section">
                    <h3>Assinaturas</h3>
                    <p>${document.getElementById('assinatura1').value}</p>
                    <p>${document.getElementById('assinatura2').value}</p>
                    <p>${document.getElementById('assinatura3').value}</p>
                    <p>${document.getElementById('assinatura4').value}</p>
                </div>
            `;
        }

        function gerarTabelaPDF(tabelaId) {
            const tabela = document.getElementById(tabelaId);
            const linhas = tabela.getElementsByTagName('tbody')[0].getElementsByTagName('tr');
            let html = '<table>';
            
            // Cabeçalho
            html += '<tr>';
            const headers = tabela.getElementsByTagName('th');
            for (let i = 0; i < headers.length - 1; i++) {
                html += `<th>${headers[i].textContent}</th>`;
            }
            html += '</tr>';
            
            // Linhas
            for (let i = 0; i < linhas.length; i++) {
                html += '<tr>';
                const inputs = linhas[i].getElementsByTagName('input');
                for (let j = 0; j < inputs.length; j++) {
                    html += `<td>${inputs[j].value}</td>`;
                }
                html += '</tr>';
            }
            
            html += '</table>';
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
