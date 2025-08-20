<script lang="tsx">
import { defineComponent, ref } from 'vue'
import TestComp from './TestComp.vue'
import TestTsxComp from './TestTsxComp.vue'

export default defineComponent({
    name: 'TsxComp',
    setup() {
        const msg = ref('ni hao')

        return () => (
            <div>
                {/*
                    Property 'onConfirmClick' does not exist on type 'IntrinsicAttributes & Partial<{}> & Omit<{ readonly modelValue: string; readonly "onUpdate:modelValue"?: ((value: string) => any) | undefined; readonly "onConfirm-click"?: (() => any) | undefined; } & VNodeProps & AllowedComponentProps & ComponentCustomProps, never>'. Did you mean '"onConfirm-click"'?ts(2322)
                  */}
                <TestComp onConfirmClick={console.log(1)} />
                <TestComp onConfirm-click={console.log(2)} />

                { /** it works */}
                <TestTsxComp v-model={msg.value} />
            </div>
        )
    }
})

</script>
