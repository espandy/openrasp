<template>
    <div class="event-detail">
        <div v-if="data.attack_type == 'sql'">
            <div class="h6">
                数据库类型
            </div>
            <p>
                {{ data.attack_params.server }}
            </p>
            <div class="h6">
                执行的SQL语句
            </div>
            <p>
                {{ data.attack_params.query }}
            </p>
        </div>

        <div v-if="data.attack_type == 'directory'">
            <div class="h6">
                读取的目录
            </div>
            <p>
                {{ data.attack_params.path }}
            </p>
            <div class="h6">
                读取的目录 - 真实路径
            </div>
            <p>
                {{ data.attack_params.realpath }}
            </p>
        </div>        

        <div v-if="data.attack_type == 'readFile'">
            <div class="h6">
                读取的文件
            </div>
            <p>
                {{ data.attack_params.path }}
            </p>
            <div class="h6">
                读取的文件 - 真实路径
            </div>
            <p>
                {{ data.attack_params.realpath }}
            </p>
        </div>      

        <div v-if="data.attack_type == 'writeFile'">
            <div class="h6">
                写入的文件
            </div>
            <p>
                {{ data.attack_params.name }}
            </p>
            <div class="h6">
                写入的文件 - 真实路径
            </div>
            <p>
                {{ data.attack_params.realpath }}
            </p>
        </div>          

        <div v-if="data.attack_type == 'include'">
            <div class="h6">
                要包含的文件
            </div>
            <p>
                {{ data.attack_params.url }}
            </p>
            <div class="h6">
                要包含的文件 - 真实路径
            </div>
            <p>
                {{ data.attack_params.realpath }}
            </p>            
        </div>     

        <div v-if="data.attack_type == 'webdav'">
            <div class="h6">
                源文件
            </div>
            <p>
                {{ data.attack_params.source }}
            </p>
            <div class="h6">
                目标文件
            </div>
            <p>
                {{ data.attack_params.dest }}
            </p>            
        </div>                    

        <div v-if="data.attack_type == 'fileUpload'">
            <div class="h6">
                上传的文件名
            </div>
            <p>
                {{ data.attack_params.filename }}
            </p>
            <div class="h6">
                上传的文件内容 - 前4KB
            </div>
            <p>
                {{ data.attack_params.content }}
            </p>
        </div>

        <div v-if="data.attack_type == 'rename'">
            <div class="h6">
                源文件
            </div>
            <p>
                {{ data.attack_params.source }}
            </p>
            <div class="h6">
                目标文件
            </div>
            <p>
                {{ data.attack_params.dest }}
            </p>
        </div>        

        <div v-if="data.attack_type == 'command'">
            <div class="h6">
                要执行的命令
            </div>
            <p>
                {{ data.attack_params.command }}
            </p>
        </div>  

        <div v-if="data.attack_type == 'xxe'">
            <div class="h6">
                要加载的外部实体
            </div>
            <p>
                {{ data.attack_params.entity }}
            </p>
        </div>         

        <div v-if="data.attack_type == 'ognl'">
            <div class="h6">
                要执行的OGNL表达式
            </div>
            <p>
                {{ data.attack_params.expression }}
            </p>
        </div>   

        <div v-if="data.attack_type == 'deserialization'">
            <div class="h6">
                要生成的Java类名
            </div>
            <p>
                {{ data.attack_params.clazz }}
            </p>
        </div>         

        <div v-if="data.attack_type == 'ssrf'">
            <div class="h6">
                要访问的 URL
            </div>
            <p>
                {{ data.attack_params.url }}
            </p>
            <div class="h6">
                IP 信息
            </div>
            <p>
                {{ data.attack_params.ip }}
            </p>                     
        </div>  

        <!-- 以下为 php 原生 -->

        <div v-if="data.attack_type == 'webshell_eval'">
            <div class="h6">
                菜刀要 eval 的内容
            </div>
            <p>
                {{ data.attack_params.eval }}
            </p>
        </div>                  

        <div v-if="data.attack_type == 'webshell_command'">
            <div class="h6">
                WebShell 要执行的命令
            </div>
            <p>
                {{ data.attack_params.command }}
            </p>
        </div>  

        <div v-if="data.attack_type == 'webshell_file_put_contents'">
            <div class="h6">
                WebShell 要写入的文件
            </div>
            <p>
                {{ data.attack_params.name }}
            </p>
            <div class="h6">
                WebShell 要写入的文件 - 真实路径
            </div>
            <p>
                {{ data.attack_params.realpath }}
            </p>
        </div>
        
        <div v-if="data.attack_type == 'callable'">
            <div class="h6">
                后门要执行的函数
            </div>
            <p>
                {{ data.attack_params.function }}()
            </p>
        </div>

    </div>

</template>

<script>

export default {
    name: 'attack_params',
    data: function () {
        return {
            data: {
                attack_params: {}
            }
        }
    },
    methods: {
        setData: function (data) {
            this.data = data
        }
    }
}
</script>

